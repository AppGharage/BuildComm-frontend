<template>
 
 <div id="signup">
    <Navigation/>

  <!--section for personal information-->  
    <div class="container" style="margin-top:60px;" >
       
        <div class="row">
            <p v-if="status">{{msg}} </p>
            <div class="col-2 col-md-3 col-lg-3"></div>
             
            <div class="col-8 col-md-6 col-lg-6">
                <h5>Personal Information</h5><hr>
                <div style="text-align:left;" >      
                    <div class="form-group">
                        <label for="fullName">Full Name</label>
                        <input type="text" class="form-control" id="name" v-model="fullName">
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                        <label for="email">Email</label>
                        <input type="email" class="form-control" id="email" v-model="email">
                        </div>
                        <div class="form-group col-md-6">
                        <label for="telephone">Telephone</label>
                        <input type="tel" class="form-control" id="telephone" v-model="telephone">
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input type="password" class="form-control" id="password" v-model="password">
                    </div>         
                </div>&nbsp;

<!--section fo community information-->
                <div style="text-align:left" >
                    <h5>Community Information</h5><hr>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                        <label for="Community Name">Community Name</label>
                        <input type="text" class="form-control" id="comp_name" v-model="communityName">
                        </div>
                        <div class="form-group col-md-6">
                        <label for="Community URL">Community URL</label>
                        <input type="url" class="form-control" id="comp_url" v-model="communityURL">
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="communityDescription">Community Description</label>
                        <textarea class="form-control" id="description" v-model="description"></textarea>
                    </div> 
                    <div class="row" style="padding-bottom:15px;">
                        <div class="col-6 col-md-4 col-lg-4">  
                        <button class="btn btn" style="background-color:#f36747;color:white; width:100%;" v-on:click="signup()">
                        <router-link to="" style="text-decoration:none;color: inherit;">Signup</router-link></button>
                        </div> 
                    </div>
                </div>
            </div>
            <div class="col-2 col-md-3 col-lg-3"></div>
        </div>
    </div>
 </div>
 </template>

<script>

import Navigation from "./Navigation";

export default {
name:'SignUp',
 components: {
   Navigation, 
  },
data() {
    return {
        fullName: "",
        email: "",
        password: "",
        telephone: "",
        communityName: "",
        communityURL: "",
        description:"", 
        loading: "",
        status: false,
        msg: ''
    };
},
methods: {  
    validate: function() {
      if( this.communityName == null || this.communityURL == null
       || this.description == null || this.fullName == null 
       || this.email == null|| this.email == null
       ||this.password == null || this.telephone == null){

            this.status = true;
            this.msg = 'All Fields are Required';
        return false;
      }else{
            this.status = false;
            return true;
      }
    }, 
    signup: function() {
        
        const communnityData = {
            community_name: this.communityName,
            community_url: this.communityURL,
            description: this.description
        };

        const valid = this.validate();

        //checking if details are valid
        if(valid){
            //request api for community details
            axios.post("https://buildcomm-api.herokuapp.com/api/community", communnityData).then(res => {
                
                if (res.data.status == true) {
                        let communityID = res.data.id;
                        // now send the user to the next route

                        const personalData = {
                            fullName: this.fullName,
                            email: this.email,
                            telephone: this.telephone,
                            password: this.password,
                            community_id: communityID
                        };

                        // Post to server
                        axios.post("https://buildcomm-api.herokuapp.com/api/users", personalData).then(res => {
                            // Post a status message
                            this.loading = "";
                            if (res.data.status == true) {
                                // now send the user to the next route
                                this.$router.push({
                                name: "Dashboard",
                                params: { user: res.data.user }
                                });
                            } else {
                                this.status = true;
                                this.msg = 'Something went Wrong!';
                            }
                        });
                        
                } else {
                    this.status = true;
                    this.msg = 'All Fields are Required';
                }
            });
           
            this.loading = "Creating your account, please wait";


        } 
      
    },
}
}
</script>

<style scoped>
/** {
    outline: 1px solid red !important;
}*/
h5{
    font-weight: 590;
    font-size: 20px;
}
hr{
    background-color: rgb(203, 223, 240);
    
}

.form-control{
  border-radius: 3px;
}
#signup{
      font-family: 'Roboto Slab', serif;

}

</style>

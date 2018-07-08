<template>
    <div id="login">
     <Navigation/>
        <div class="container">
            <!-- Display login status -->
            <div id="status"></div>
            <!-- Display user profile data -->
            <div id="userData"></div>
            <div class="row">
                <div class="col-2  col-md-3 col-lg-4"></div>
                <div class="col-2  col-md-3 col-lg-4">
                </div>
                    <div class="col-8 col-md-6 col-lg-4">
                        <form id="signIn" style="margin-top:90px; text-align:left">
                            <div class="form-group">
                                <label for="email">Email address</label>
                                <input type="email" class="form-control" id="email"  placeholder="Enter email" v-model="email">
                            </div>
                            <div class="form-group">
                                <label for="password">Password</label>
                                <input type="password" class="form-control" id="password" placeholder="Password" v-model="password">
                            </div>
                            <div class="row">
                                <div class="col-6 col-md-4 col-lg-4">  
                            <button  class="btn btn"  value="submit" style="background-color:#f36747;color:white; width:100%;" v-on:click="signin()">
                                <router-link to="" style="text-decoration:none;color: inherit;">Login</router-link></button>                            </div> 
                            
                        <!-- Facebook login or logout button -->
                        <a href="javascript:void(0);" onclick="fbLogin()" id="fbLink" class="btn btn-sm btn-info">Connect with Facebook</a>
                            </div>  
                                            
                        </form> 

                    </div>
            </div>  
        </div>
    </div>
</template>

<script>
import Navigation from './Navigation';

export default {
    name :'SignIn',
    components:{
        Navigation
    },
    data() {
    return {
        email: "",
        password: "",
        loading: "",
        status: false,
        msg: ''
    };
},
  
  methods: {
    validate: function() {
      if(  this.email == null ||this.password == null ){
            
            this.status = true;
            this.msg = 'All Fields are Required';
        return false;
      }else{
            this.status = false;
            return true;
      }
    }, 
        signin: function() {
           const logIn = {
                email: this.email,
                password: this.password
            };   
            const validation = this.validate();
            
            if(validation){
                axios.post("https://buildcomm-api.herokuapp.com/api/users", logIn).then(res => {
                    this.loading = "";
                    if (res.data.status == true) {
                        // now send the user to the next route
                        this.$router.push({
                        name: "Dashboard",
                        params: { user: res.data.user }
                        });
                    } else {
                        this.status = true;
                        this.msg = 'Email or Password incorrect';
                    }
                });
            }
  }
}
}
</script>

<style scoped>
header {
  margin: 0;
  height: 56px;
  padding: 0 16px 0 24px;
  background-color: #f36747;
  color: #ffffff;
}

header span {
  display: block;
  position: relative;
  font-size: 20px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
}
.form-control{
  border-radius: 3px;
}
#login{
      font-family: 'Roboto Slab', serif;

}
#Navigation{
color: #ffffff;
font-family: 'Roboto Slab', serif;
font-weight: 30px;
}
</style>

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
                                <input type="email" class="form-control" id="email"  placeholder="Enter email">
                            </div>
                            <div class="form-group">
                                <label for="password">Password</label>
                                <input type="password" class="form-control" id="password" placeholder="Password">
                            </div>
                            <div class="row">
                                <div class="col-6 col-md-4 col-lg-4">  
                            <button type="submit" class="btn btn"  value="submit" style="background-color:#f36747;color:white; width:100%;">
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
    data: function ()  {
    return {
      model: {
        email: "",
        password: "",
      },
      loading: "",
      status: ""
    };
  },
  methods: {
    login() {
        const formData = new FormData();

        formData.append("email", this.model.email);
        formData.append("password", this.model.password);
        this.loading = "Signing in";
       
        // Post to server
        axios.post("http://buildcomm-api.herokuapp.com/users", formData).then(res => {
            
            // Post a status message
            this.loading = "";

        //if validation from api succeeds
            if (res.data.status == true) {
        // now send the user to the next route
                this.$router.push({
                    name: "Dashboard",
                    params: { user: res.data.user }
                });
            } else {
                this.status = res.data.message;
            }
        });
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

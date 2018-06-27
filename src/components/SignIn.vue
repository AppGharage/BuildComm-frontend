<template>
    <div id="login">
     
        <div class="container">
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
                            <input class="btn" type="submit" value="Signin" v-on:click="login()" style="background-color:#f36747; color:#fff;width:100%">
                            </div> 
                        </div>  
                                            
                    </form>  
                        </div>
                    </div>
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
    data: {
    errors: [],
    name: null,
    email: null,
    movie: null
  },
 

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

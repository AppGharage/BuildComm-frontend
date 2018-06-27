<template>
<div>
 
    <div id="Navigation">
          <header>
            <nav class="navbar">
                  <a class="navbar-brand">BuildComm</a>
              <form class="form-inline">
                  <button type="button" class="btn btn-outline-light" role="button"><router-link to="login" 
                  style="text-decoration:none;color: inherit;">Login</router-link>
                  </button>&nbsp;&nbsp;           
                  <button type="button" class="btn btn" style="background-color:#456F93;color:white">
                    <router-link to="signup" style="text-decoration:none;color: inherit;">Signup</router-link></button>
              </form>
            </nav>
      
          </header>   
    </div>
</div>
</template>


<script>
export default {
  name: 'Navigation',
  
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
  border-radius: 19px;
}
#Navigation{
color: #ffffff;
font-family: 'Roboto Slab', serif;
font-weight: 30px;
}</style>


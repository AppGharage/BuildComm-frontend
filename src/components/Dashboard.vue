<template>
<div class="Dashboard">
  
          <header >
            <nav class="navbar" >
                  <a class="navbar-brand">BuildComm</a>
              <form class="form-inline">
                          <i class="fas fa-user-circle" style="font-size:30px;"></i>
              </form>
            </nav>
      
          </header>   

          <!-- start second nav-->
    <header>
        <nav class="navbar navbar-expand-lg navbar-light shadow  bg-white rounded" style="background-color:#fff; "> 
            <div class="row justify-content-start" style=" margin:0 auto;width:100%;">
                <a class="navbar-brand" href="#" style=" color: #f36747; ">Send Notification</a>

                <a class="navbar-brand" href="#" style=" color: #f36747;">Connect to Facebook</a>              
            
                <a class="navbar-brand" href="#" style=" color: #f36747;">Advertise</a>
            
                <a class="navbar-brand" href="#" style=" color: #f36747;">Search</a>
            
                <a class="navbar-brand" href="#" style=" color: #f36747;">Settings</a>
                
            </div> 
        </nav>
   </header>

   <!--card section-->
<div class="container">
   <div class="row" >
       <div class="col-lg-3 col-md-6 col-sm-3 " style="padding:10px">
           <div class="card" >
            <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
            </div>
       </div>
       <div class="col-lg-3 col-md-6 col-sm-3 " style="padding:10px">
           <div class="card" >
            <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
            </div>
       </div>
       <div class="col-lg-3 col-md-6 col-sm-3" style="padding:10px">
           <div class="card" >
            <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
            </div>
       </div>
       <div class="col-lg-3 col-md-6 col-sm-3" style="padding:10px">
           <div class="card" >
            <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="card-link">Card link</a>
                <a href="#" class="card-link">Another link</a>
            </div>
            </div>
       </div>
   </div>
    </div>
</div>


</template>

<script>

export default {
name:'Dashboard'
}    
</script>

<style scoped>
html,
body {
  overflow-x: hidden; /* Prevent scroll on narrow devices */
}
.navbar{
      background-color: #f36747;
      color:white; 

}

.container{
    width: 100%;   
    padding: 15px; 
    display: flex;
}


</style>

<template>
    <div class="settings">
        <header >
            <nav class="navbar navbar- navbar-light shadow  bg-white rounded" >
                          <i class="fas fa-user-circle" style="font-size:30px;"></i>
              <form class="form-inline">
            <button type="button" class="btn btn-primary">Save</button>
             
            </form>
            </nav>
        </header> 

        <div class="row" style="padding:20px;">
            <div class="col-sm-3"></div>
                <div class="col-sm-6" >
                    <div class="card">
                        <div class="card-body">
                            <div class="row justify-content-center" ><h5>Connect to other platforms here</h5></div>
                                <div class="row  justify-content-center" style="padding:25px; ">                      
                                <button type="button" class="btn btn-primary" style="width:80%">Facebook</button>
                                </div>
                                <div class="row  justify-content-center" style="padding:25px; ">                      
                                <button type="button" class="btn btn-warning" style="width:80%">Slack</button>
                                </div>
                            
                        </div>
                    </div>
                </div>
            <div class="col-sm-3"></div>
        </div>

        <div class="row" style="padding:20px;">
            <div class="col-sm-3"></div>
                <div class="col-sm-6" >
                    <div class="card">
                         <div class="card-body">
                            <div class="row justify-content-center" ><h5>Change Password</h5></div>
                                <div class="row  justify-content-center" style="padding:20px"> 
                                    <div class="col-10 col-sm-8">
                                        <label for="">Old Password:</label>                     
                                        <input type="password" >
                                    </div>
                                </div>
                                    <div class="row  justify-content-center" style="padding:20px;"> 
                                    <div class="col-10 col-sm-8">
                                        <label for="">New Password:</label>                     
                                        <input type="password" >
                                    </div>
                                </div>                             
                        </div>
                    </div>
                </div>
            <div class="col-sm-3"></div>
        </div>
    </div>
</template>

<script>
export default {
    name :'settings',
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





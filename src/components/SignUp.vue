<template>
 
 <div id="signup">
    <Navigation/>
    
    <div class="container" style="margin-top:60px;">
        <div class="row">
            <div class="col-2 col-md-3 col-lg-3"></div>
            <div class="col-8 col-md-6 col-lg-6">
                <h5>Personal Information</h5><hr>
                <form style="text-align:left;">      
                    <div class="form-group">
                        <label for="Name">Full name</label>
                        <input type="text" class="form-control" id="name"  >
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                        <label for="email">Email</label>
                        <input type="email" class="form-control" id="email" >
                        </div>
                        <div class="form-group col-md-6">
                        <label for="telephone">Telephone</label>
                        <input type="tel" class="form-control" id="telephone" >
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input type="password" class="form-control" id="pw" >
                    </div>         
                </form>&nbsp;

                <form style="text-align:left">
                    <h5>Community Information</h5><hr>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                        <label for="Cname">Community Name</label>
                        <input type="Cname" class="form-control" id="Cname" >
                        </div>
                        <div class="form-group col-md-6">
                        <label for="Curl">Community URL</label>
                        <input type="Curl" class="form-control" id="Curl" >
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="exampleFormControlTextarea1">Company Desciption</label>
                        <textarea class="form-control" id="exampleFormControlTextarea1" ></textarea>
                    </div>

                    
                    <div class="row" style="padding-bottom:15px;">
                        <div class="col-6 col-md-4 col-lg-4">  
                        <input class="btn" type="submit" value="Submit" style="background-color:#f36747; color:#fff;width:100%;">
                        </div> 
                    </div>
                </form>
            </div>
            <div class="col-2 col-md-3 col-lg-3"></div>
        </div>
    </div>
 </div>
 </template>

<script>

export default {
name:'SignUp',
components: {
    
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

<template>
    <div class="result-hero">
        <navbar/>
        <div class="container ">
            <div class="row text-center mt-5">
                <div class="col-md-12">
                    <div class="pro-img mt-5">
                        <img src="../assets/images/person.jpg" alt="">
                    </div>
                    <div class="result-text">
                        <h1>Abdelrahman Talaat Ahmed</h1>
                        <h2>Congratulations </h2>
                        <span style="color:#ffffff;">You’ve been nominated for faculty of</span>
                        <h2>Engineering</h2>
                        <p style="color:#ffffff;">Which you can find in….</p>
                    </div>
                </div>
            </div>
            <div class="row text-center" style="border-top:1px solid #ffffff">
                <div class="col-md-6">
                    <h1 class="uni-head">university</h1>
                </div>
                <div class="col-md-6">
                    <h1 class="uni-head">location</h1>
                </div>
            </div>
            <div class="row text-center">
                <div class="col-md-6" style="border-right:1px solid #ffffff">
                    <h3 class="result-uni">Horus</h3>
                </div>
                <div class="col-md-6">
                    <h3 class="result-uni">Damita</h3>
                </div>
            </div>
            <div class="row text-center">
                <div class="col-md-6" style="border-right:1px solid #ffffff">
                    <h3 class="result-uni">cairo</h3>
                </div>
                <div class="col-md-6" >
                    <h3 class="result-uni">cairo</h3>
                </div>
            </div>
            <div class="row text-center">
                <div class="col-md-6" style="border-right:1px solid #ffffff">
                    <h3 class="result-uni">Met</h3>
                </div>
                <div class="col-md-6" >
                    <h3 class="result-uni">mansora</h3>
                </div>
            </div>
            <div class="row text-center">
                <div class="col-md-6" style="border-right:1px solid #ffffff">
                    <h3 class="result-uni">delta</h3>
                </div>
                <div class="col-md-6" >
                    <h3 class="result-uni">gamasa</h3>
                </div>
            </div>
            <v-card-actions>
            <v-btn class="load-infobtn mt-5">load more information</v-btn>
          </v-card-actions>
        </div>
    </div>
</template>
<script>
import navbar from '~/components/navbar.vue'
export default {
  components: { navbar },
    
}
</script>
<style>
    
</style>
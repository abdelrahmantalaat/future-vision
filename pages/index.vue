<template>
<div>
  <header class="uni-info-pageheader">
     <navbar />
     <div class="container-fluid pr-5 pl-5">
         <div class="row ">
             <div class="col-md-6" style="margin-top:180px">
                 <p class="uni-info-pageheader-text mt-5" >Elite egyptian universities that 
have leadership in 
education services and scientific 
research locally, regionally 
and internationally.</p>
<nuxt-link to="/login" class="btn main-login ">login</nuxt-link>
          <div>
            <nuxt-link to="/signup" class="btn main-signup">sign up</nuxt-link>
          </div>
             </div>
             <div class="col-md-6"  style="margin-top:150px">
                 <div class="row">
                     <div class="col-md-7">
                        <img src="../assets/images/russian.png" class="uni-info-pageheader-img" alt="">
                     </div>
                     <div class="col-md-5 pt-5 ">
                         <img src="../assets/images/alamin.png"  class="uni-info-pageheader-img" alt="">
                     </div>
                 </div>
                 <div class="row">
                     <div class="col-md-5 pt-5 ">
                         <img src="../assets/images/stud.png"  class="uni-info-pageheader-img" alt="">
                     </div>
                     <div class="col-md-7">
                        <img src="../assets/images/hoaras.png" class="uni-info-pageheader-img" alt="">
                     </div>
                     
                 </div>
             </div>
         </div>
         
     </div>

  </header>
  
    <section class="uni-main" id="universities">
     
         
         
    <v-carousel>
    <v-carousel-item
      
      
    >
         <div class="container uni-con">
           <div class="uni-cover">
             <img src="../assets/images/hoaras.png" alt="">
         </div>
         <div class="uni-layer"></div>
             <div class="row uni-row" style="margin-top:180px">
                 <div class="col-md-6">
                     <div class="uni-img">
                          <img src="../assets/images/hoaras.png" alt="">
                     </div>
                 </div>
                 <div class="col-md-6 mt-5">
                     <h1 class="uni-name">Horus</h1>
                     <h1 class="uni-name">University</h1>
                     <div class="college-slide">
                        <VueSlickCarousel v-bind="slickOptions" >
                            <div>faculty of nursing</div>
                            <div>faculty of engineering</div>
                            <div>faculty of medicine</div>
                            <div>faculty of culture</div>
                        </VueSlickCarousel>
                     </div>
                     <div class="location">
                         <img src="../assets/images/Path 5.png" alt="" style="display:inline-block;">
                         <span>Cairo</span>
                     </div>
                 </div>
             </div>
         </div>
    </v-carousel-item>
    <v-carousel-item
      
      reverse-transition="fade-transition"
      transition="fade-transition"
    >
      <div class="container uni-con">
           <div class="uni-cover">
             <img src="../assets/images/russian.png" alt="">
         </div>
         <div class="uni-layer"></div>
             <div class="row uni-row" style="margin-top:180px">
                 <div class="col-md-6">
                     <div class="uni-img">
                          <img src="../assets/images/russian.png" alt="">
                     </div>
                 </div>
                 <div class="col-md-6 mt-5">
                     <h1 class="uni-name">russian</h1>
                     <h1 class="uni-name">University</h1>
                     <div class="college-slide">
                        <VueSlickCarousel v-bind="slickOptions" >
                            <div>faculty of nursing</div>
                            <div>faculty of engineering</div>
                            <div>faculty of medicine</div>
                            <div>faculty of culture</div>
                        </VueSlickCarousel>
                     </div>
                     <div class="location">
                         <img src="../assets/images/Path 5.png" alt="" style="display:inline-block;">
                         <span>Cairo</span>
                     </div>
                 </div>
             </div>
         </div>   
    </v-carousel-item>
    </v-carousel>
    
   </section>
    
 

    
   
   
 
  
</div>

</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import navbar from '../components/navbar.vue'
export default {
  components: { navbar,VueSlickCarousel, },
  name: 'MyComponent',  
  data() {
      return {
         slickOptions:{
             autoplay:true,
              autoplaySpeed:1500
         }, 
         slickOptions2:{
           arrows:true,
           dots:true
         }
         
      }
  },
};
</script>
<style></style>

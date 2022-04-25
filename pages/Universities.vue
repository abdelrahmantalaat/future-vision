<template>
    <div>
     <header class="uni-info-pageheader">
     <navbar />
     <div class="container">
         <div class="row " style="margin-top:180px;">
             <div class="col-md-6">
                 <h3 class="uni-info-pageheader-text mt-5" >Elite egyptian universities that 
have leadership in 
education services and scientific 
research locally, regionally 
and internationally.</h3>
             </div>
             <div class="col-md-6">
                 <div class="row">
                     <div class="col-md-6">
                        <img src="../assets/images/russian.png" class="uni-info-pageheader-img" alt="">
                     </div>
                     <div class="col-md-4 pt-5 ">
                         <img src="../assets/images/alamin.png"  class="uni-info-pageheader-img" alt="">
                     </div>
                 </div>
                 <div class="row">
                     <div class="col-md-4 pt-5 ">
                         <img src="../assets/images/stud.png"  class="uni-info-pageheader-img" alt="">
                     </div>
                     <div class="col-md-6">
                        <img src="../assets/images/hoaras.png" class="uni-info-pageheader-img" alt="">
                     </div>
                     
                 </div>
             </div>
         </div>
     </div>

     </header>   
     <section class="uni-main">
         <div class="uni-cover">
             <img src="../assets/images/hoaras.png" alt="">
         </div>
         <div class="uni-layer"></div>
         <div class="container">
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
                         <img src="../assets/images/Path 5.png" alt="">
                         <span>Cairo</span>
                     </div>
                 </div>
             </div>
         </div>
     </section>
    </div>
</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import navbar from '../components/navbar.vue'
// import { Icon } from '@iconify/vue';
export default {
  components: { navbar,VueSlickCarousel, },
  name: 'MyComponent',  
  data() {
      return {
         slickOptions:{
             autoplay:true,
              autoplaySpeed:1500
         } 
      }
  },
}
</script>
<style>
    
</style>
<template>
<div>
  <header class="uni-info-pageheader">
     <navbar />
     <h1 v-if="$auth.loggedIn"> {{ user.firstname }} </h1>
     <div class="container-fluid pr-5 pl-5">
         <div class="row ">
             <div class="col-md-6" style="margin-top:180px">
                 <p class="uni-info-pageheader-text mt-5" >
                   <span>Welcome to Future Vision ..</span> <br>
Where we will help you find out the the college that suits your interests.
Answer some few questions and let the rest for us.</p>
<nuxt-link to="/login" class="btn main-login ">Login</nuxt-link>
          <div>
            <nuxt-link to="/signup" class="btn main-signup">Sign up</nuxt-link>
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
      :key="index"
            v-for="(list, index) in lists"
      reverse-transition="fade-transition"
      transition="fade-transition"
    >
      <div class="container uni-con">
           <div class="uni-cover">
             <img :src="list.university_image" alt="">
         </div>
         <div class="uni-layer"></div>
             <div class="row uni-row" style="margin-top:180px">
                 <div class="col-md-6">
                     <div class="uni-img">
                          <img :src="list.university_image" alt="">
                     </div>
                 </div>
                 <div class="col-md-6 mt-5">
                     <h1 class="uni-name">{{ list.name }}</h1>
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
                         <span>{{ list.location }} </span>
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
          lists:[],
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
  async fetch() {
    await this.getuniversities()
  },
  methods:{
   async getuniversities() {
      const unversity = this.$axios.get("/list")
      this.lists = await unversity
      

    },
  }
};
</script>
<style></style>

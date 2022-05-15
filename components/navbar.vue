<template v-slot:activator="{ on, attrs }">
  <nav class="navbar navbar-expand-lg">
    <div class="container-fluid">
      <nuxt-link class="navbar-brand" to="/"
        ><img src="../assets/images/main-logo.png" alt=""
      /></nuxt-link>
     
       <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-item ><nuxt-link class="nav-link" aria-current="page" to="/#universities"
              >universities</nuxt-link
            ></b-nav-item>
        <b-nav-item ><nuxt-link class="nav-link" aria-current="page" to="question"
              >College Test</nuxt-link
            ></b-nav-item>
            <b-nav-item ><nuxt-link class="nav-link" aria-current="page" to="result"
              >College result</nuxt-link
            ></b-nav-item>
            
        <b-nav-item-dropdown right
        >
          
          <template #button-content>
            <em><img src="../assets/images/person.jpg" class="nav-img" alt="">
            </em>
          </template>
          <b-dropdown-item><nuxt-link class="drop-link" to="profile">profile</nuxt-link></b-dropdown-item>
          <b-dropdown-item>Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>

     
    </b-collapse>
    </div>
    
  </nav>
</template>
<script>
  export default {

  }
</script>
<style>
.nav-img {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-top: -12px;
}
.dropdown-toggle::after{
  display: none !important;
}
.drop-link{
  color: #000;
  text-decoration: none;
}
.drop-link:hover{
  color: #000;
  text-decoration: none;
}
</style>

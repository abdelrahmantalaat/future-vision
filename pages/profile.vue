<template>
  <div>
    <navbar />
    <section class="profile-info-sec">
      <div class="container">
        <div class="row mt-5">
          <div class="col-md-4">
            <div class="profile-img">
              <img src="../assets/images/person.jpg" alt="" />
            </div>
          </div>
          <div class="col-md-8">
            <div class="profile-info">
              <!-- <h1>Hi {{ user.firstname }}</h1> -->

              <p>Age : 21</p>
              <nuxt-link class="pro-info-btn" to="edit-profile"
                >Edit Profile</nuxt-link
              >
            </div>
          </div>
        </div>
        <div class="row pro-info-row">
          <div
            class="col-md-4 text-center"
            style="border-right: 1px solid #000"
          >
            <img
              style="width: 50px; height: 50px"
              src="../assets/images/percentage.png"
              alt=""
            />
            <h3 style="color: #3557a2; font-weight: bold">92</h3>
          </div>
          <div
            class="col-md-4 text-center"
            style="border-right: 1px solid #000"
          >
            <img
              style="width: 50px; height: 50px"
              src="../assets/images/placeholder.png"
              alt=""
            />
            <h3 style="color: #3557a2; font-weight: bold">cairo</h3>
          </div>
          <div class="col-md-4 text-center">
            <img
              style="width: 50px; height: 50px"
              src="../assets/images/user-2.png"
              alt=""
            />
            <h3 style="color: #3557a2; font-weight: bold">Scientific</h3>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="container p-5 more-info-con">
        <div class="row p-3 more-info-row">
          <div class="col-md-4">
            <div class="more-info-img">
              <img src="../assets/images/signbac.png" alt="" />
            </div>
          </div>
          <div class="col-md-8 text-center">
            <div class="more-info-text">
              <h1>Engineering result</h1>
              <h2>20%</h2>
            </div>
          </div>
        </div>
        <div class="row p-5 more-info-row">
          <div class="col-md-4">
            <div class="more-info-img">
              <img src="../assets/images/signbac.png" alt="" />
            </div>
          </div>
          <div class="col-md-8 text-center">
            <div class="more-info-text">
              <h1>medicine result</h1>
              <h2>20%</h2>
            </div>
          </div>
        </div>
        <div class="row">
          <nuxt-link class="btn new-test" to="question"
            >Start new test</nuxt-link
          >
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import navbar from "~/components/navbar.vue";

export default {
  async fetch() {
    await this.$auth.fetchUser();
    
  },
  components: { navbar },
  data() {
    return {};
  },
};
</script>
<style>
</style>

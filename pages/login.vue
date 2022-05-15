<template>
  <div>
    <v-main class="login-hero">
      <div class="baclog-img">
        <img src="../assets/images/signbac.png" alt="" />
      </div>

      <v-container fluid style="padding: 40px">
        <v-row>
          <v-col cols="12" md="6">
            <div class="logtext text-center">
              <h2 class="font-weight-bold">Welcome...</h2>
              <h2>Want to know the best college for you....?!</h2>
              <h3 class="mt-3 font-weight-bold text-justify">
                Just login or create new account then answer some questions and
                you will know the best college for you...
              </h3>
            </div>
          </v-col>
          <v-col cols="12" md="6">
            <v-form v-model="valid" class="loginForm">
              <v-row>
                <v-col cols="12" md="12">
                  <v-text-field
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="12" md="12">
                  <v-text-field
                    v-model="password"
                    :rules="passwordRules"
                    label="Password"
                    type="password"
                    required
                  ></v-text-field>
                  
                  <p class="forget-btn">forget password</p>
                </v-col>
                
              </v-row>

              <v-card-actions>
                <v-container>
                   <v-row>
                 <v-btn class="loginbtn" @click="loginHandler">Login</v-btn>
                </v-row>
                
                <v-row>
                  <v-col cols="12" class="text-center">
                      <nuxt-link to="/signup" class="create-btn"
                    ><span>create account</span></nuxt-link
                  >
                </v-col>
                </v-row>
                </v-container>
                
                
                
              </v-card-actions>
            </v-form>
          </v-col>
        </v-row>
      </v-container>
      <navbar style="border-bottom: 1px solid #ffffff" />
    </v-main>
  </div>
</template>
<script>
import navbar from "../components/navbar.vue";
export default {
  data: () => ({
    valid: false,

    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
    password: "",
    passwordRules: [(v) => !!v || "password is required"],
  }),
  methods: {
    async loginHandler() {
      const formdata = {
        email: this.email,
        password: this.password,
      };
      this.$auth
        .loginWith("local", { data: formdata })
        .then((response) => {
          this.$router.push(this.localePath("/"));
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style></style>

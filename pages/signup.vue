<template>
  <v-app>
    <v-main class="sign-hero">
      <div class="logo">
        <nuxt-link to="/">
          <img src="../assets/images/main-logo.png" alt="logo" />
        </nuxt-link>
      </div>

      <v-container style="padding: 40px">
        <v-form>
          <v-row>
            <div class="info-type">
              <p>New user</p>
            </div>
            <v-col
              cols="12"
              md="6"
              style="padding-left: 70px; padding-right: 70px"
            >
              <v-row>
                <div class="info-type">
                  <p>personal information</p>
                </div>
              </v-row>
              <v-text-field
                name="firstname"
                label="first name"
                type="text"
                :rules="firstnameRules"
                class="input"
                v-model="firstname"
              ></v-text-field>
              <v-text-field
                name="lastname"
                label="last name"
                type="text"
                :rules="lastnameRules"
                class="input"
                v-model="lastname"
              ></v-text-field>
              <v-text-field
                name="email"
                label="Email"
                :rules="emailRules"
                type="email"
                class="input"
                v-model="email"
              ></v-text-field>
              <v-text-field
                name="password"
                :type="!showPassword ? 'password' : 'text'"
                label="password"
                :rules="passwordRules"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                @click:append="showPassword = !showPassword"
                class="input"
                v-model="password"
              ></v-text-field>

              <v-text-field
                name="confirm password"
                label="confirm password"
                :rules="confirmPasswordRules"
                type="text"
                class="input"
                v-model="password"
              >
              </v-text-field>
              <v-menu
                ref="menu1"
                v-model="menu1"
                :close-on-content-click="false"
                transition="scale-transition"
                offset-y
                max-width="290px"
                class="input"
                min-width="auto"
              >
                <template v-slot:activator="{ on, attrs }">
                  <v-text-field
                    v-model="dateFormatted"
                    label="Date of birth"
                    persistent-hint
                    v-bind="attrs"
                    @blur="date = parseDate(dateFormatted)"
                    v-on="on"
                  ></v-text-field>
                </template>
                <v-date-picker
                  v-model="date"
                  no-title
                  @input="menu1 = false"
                ></v-date-picker>
              </v-menu>
              <v-select
                v-model="locationSeclected"
                :items="location"
                label="location"
              ></v-select>
              <v-radio-group v-model="gender" mandatory>
                <v-row>
                  <v-col><v-radio label="male" value="male"></v-radio></v-col>
                  <v-col>
                    <v-radio label="female" value="female"></v-radio>
                  </v-col>
                </v-row>
              </v-radio-group>

              <v-file-input
                accept="image/*"
                label="profile image"
                v-model="imageselected"
              ></v-file-input>
            </v-col>
            <v-col
              cols="12"
              md="6"
              style="padding-left: 70px; padding-right: 70px"
            >
              <v-row>
                <div class="info-type">
                  <p>High school result</p>
                </div>
              </v-row>

              <v-radio-group v-model="departments" mandatory>
                <v-row>
                  <v-col
                    ><v-radio label="Scientific" value="Scientific"></v-radio
                  ></v-col>
                  <v-col>
                    <v-radio label="Literary" value="Literary"></v-radio>
                  </v-col>
                </v-row>
              </v-radio-group>

              <v-text-field
                name="arabicmark"
                label="Arabic mark"
                type="text"
                class="input"
                v-model="arabicmark"
                :rules="lecrule"
              ></v-text-field>
              <v-text-field
                name="englishmark"
                label="english mark"
                type="text"
                class="input"
                v-model="englishmark"
                :rules="lecrule"
              ></v-text-field>
              <v-text-field
                name="thirdlangmark"
                label="3rd languge mark"
                type="text"
                class="input"
                v-model="thirdlangmark"
                :rules="lecrule"
              ></v-text-field>
              <div style="width: 100%" v-if="this.departments == 'Scientific'">
                <v-text-field
                  name="chemistrymark"
                  label="chemistry mark"
                  type="text"
                  class="input"
                  v-model="chemistrymark"
                  :rules="lecrule"
                ></v-text-field>
                <v-text-field
                  name="physicsmark"
                  label="physics mark"
                  type="text"
                  class="input"
                  v-model="physicsmark"
                  :rules="lecrule"
                ></v-text-field>
                <v-text-field
                  name="geologymark"
                  label="geology mark"
                  type="text"
                  class="input"
                  v-model="geologymark"
                  :rules="lecrule"
                ></v-text-field>
                <v-text-field
                  name="mathmark"
                  label="math mark"
                  type="text"
                  class="input"
                  v-model="mathmark"
                  :rules="lecrule"
                ></v-text-field>
              </div>
              <div style="width: 100%" v-if="this.departments == 'Literary'">
                <v-text-field
                  name="Philosophymark"
                  label="Philosophy mark"
                  type="text"
                  class="input"
                  v-model="Philosophymark"
                  :rules="lecrule"
                ></v-text-field>

                <v-text-field
                  name="historymark"
                  label="history mark"
                  type="text"
                  class="input"
                  v-model="historymark"
                  :rules="lecrule"
                ></v-text-field>
                <v-text-field
                  name="Geographymark"
                  label="Geography mark"
                  type="text"
                  class="input"
                  v-model="Geographymark"
                  :rules="lecrule"
                ></v-text-field>
                <v-text-field
                  name="psychologymark"
                  label="psychology mark"
                  type="text"
                  class="input"
                  v-model="psychologymark"
                  :rules="lecrule"
                ></v-text-field>
              </div>
              <v-text-field
                name="percentage"
                label="percentage %"
                type="text"
                class="input"
                v-model="percentage"
                :rules="lecrule"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-card-actions>
            <v-btn class="signbtn" @click="signupHandler">Signup</v-btn>
          </v-card-actions>
        </v-form>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import navbar from "../components/navbar.vue";
export default {
  components: { navbar },
  theme: {
    options: {
      customProperties: true,
    },
  },
  name: "Signup",
  data: (vm) => ({
    date: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
      .toISOString()
      .substr(0, 10),
    dateFormatted: vm.formatDate(
      new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
        .toISOString()
        .substr(0, 10)
    ),
    menu1: false,
    menu2: false,
    firstname: "",
    lastname: "",
    firstnameRules: [(v) => !!v || "first name is required"],
    lastnameRules: [(v) => !!v || "last name is required"],
    picker: null,
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
    password: "",
    confirmpassword: "",
    passwordRules: [(v) => !!v || "password is required"],
    confirmPasswordRules: [
      (v) => !!v || "confirm password is required",
      // (value) =>
      //   value == password || 'The password confirmation does not match.',
    ],
    confirmpassword: "",
    locationSeclected: null,
    location: ["mansora", "cairo", "alex", "egypt"],

    departments: "",
    arabicmark: null,
    lecrule: [(v) => !!v || "Required.", (v) => (v || "") <= 100 || "Max 100"],
    physicsmark: null,
    mathmark: null,
    chemistrymark: null,
    englishmark: null,
    thirdlangmark: null,
    geologymark: null,
    Philosophymark: null,
    historymark: null,
    Geographymark: null,
    psychologymark: null,
    percentage: null,
    imageselected: "",
    showPassword: false,
    gender: "",
  }),

  computed: {
    computedDateFormatted() {
      return this.formatDate(this.date);
    },
  },
  watch: {
    date(val) {
      this.dateFormatted = this.formatDate(this.date);
    },
  },
  methods: {
    //  chosefile(){

    //    const img = document.querySelector('#photo');
    //    const choosedFile = this.image[0];
    //    if (choosedFile) {

    //       const reader = new FileReader();

    //       reader.addEventListener('load', function(){
    //           img.setAttribute('src', reader.result);
    //       });

    //       reader.readAsDataURL(choosedFile);

    //   }
    //  },
    formatDate(date) {
      if (!date) return null;

      const [year, month, day] = date.split("-");
      return `${month}/${day}/${year}`;
    },
    parseDate(date) {
      if (!date) return null;

      const [month, day, year] = date.split("/");
      return `${year}-${month.padStart(2, "0")}-${day.padStart(2, "0")}`;
    },
    async signupHandler() {
      const data = {
        firstname: this.firstname,
        lastname: this.lastname,

        email: this.email,
        password: this.password,

        birth: this.dateFormatted,
        location: this.locationSeclected,
        department: this.departments,
        arabicMark: this.arabicmark,
        physicsMark: this.physicsmark,
        mathMark: this.mathmark,
        chemistryMark: this.chemistrymark,
        englishMark: this.englishmark,
        thirdlangmark: this.thirdlangmark,
        geologymark: this.geologymark,
        Philosophymark: this.Philosophymark,
        historymark: this.historymark,
        psychologymark: this.psychologymark,
        totalPercentage: this.percentage,
        img: this.imageselected,
        gender: this.gender,
      };

      this.$axios
        .post("https://625c1367c9e78a8cb9b36430.mockapi.io/users", data)
        .then((res) => {
          this.$router.push("/login");
          // if (res !== undefined && res.status == 200) {

          //   console.log(data)
          // }
        });
    },
  },
};
</script>

<style>
.logo {
  position: absolute;
  left: 0;
  top: 0;
}
.logo img {
  width: 200px;
  height: auto;
}
.sign-hero {
  height: auto;
  background-image: url(../assets/images/signbac.png);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.main-card {
  background: none !important;
  border: none;
}
.info-type {
  text-align: center;
  width: 100%;
}
.info-type p {
  color: #ffcc53;
  font-size: 30px;
  font-weight: bold;
}

.v-card__actions > .v-btn.v-btn {
  margin-right: auto !important;
  margin-left: auto !important;
  width: 300px;
  height: 50px;
  background: none;
  border: 4px solid #ff892f;
  border-radius: 20px;
  color: #ffffff;
}
.v-sheet.v-card {
  border: none !important;
}
.v-application .elevation-12 {
  border: none !important;
  background: none !important;
  box-shadow: none !important;
}
.profile-pic-div {
  height: 100px;
  width: 100px;

  border-radius: 50%;
  overflow: hidden;
  border: 1px solid grey;
}

#photo {
  height: 100%;
  width: 100%;
}

/* #file{
    display: none;
} */
</style>

<template>
  <div id="app">
    <v-app id="inspire">
      <!-- <v-card-title>
      <v-text-field
        v-model="search"
        append-icon="search"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title> -->
      <div>
        <!-- <v-data-table
        :headers="headers"
        :items="desserts"
        :search="search"
        :page.sync="page"
        :items-per-page="itemsPerPage"
        class="elevation-1"
        @page-count="pageCount = $event"
        @pagination="doSomething"
      ></v-data-table> -->
      <v-card
      :key="index"
            v-for="(item, index) in items"
            :page.sync="page"
        :items-per-page="itemsPerPage"
        
        @page-count="pageCount = $event"
        @pagination="doSomething"
            >
              <div 
           
            class="question">
              <p>{{ item.body }}</p>
              <div class="answers mt-5">
                <v-radio-group  mandatory>
                  <v-row>
                    <v-col v-for="(answer, index) in item.answers" :key="index"
                      ><v-radio
                        :label="answer.text"
                        :value="answer.value"
                        
                      ></v-radio
                    ></v-col>
                  </v-row>
                </v-radio-group>
              </div>
            </div>
            </v-card>
    
        <div class="text-center pt-2">
          <span>{{ pagination }}</span>
          <v-pagination v-model="page" :length="pageCount"></v-pagination>
        </div>
      </div>
    </v-app>
  </div>
</template>
<script>
import Navbar from "../components/navbar.vue";

export default {
  data() {
    return {
      items: [
        {
          title: "question1",
          type: "engineer",
          body: "what is your last name?",
          answers: [
            {
              text: "kareem",
              value: "kareem",
            },
            {
              text: "ahmed",
              value: "ahmed",
            },
            {
              text: "ali",
              value: "ali",
            },
            {
              text: "omar",
              value: "omar",
            },
          ],
        },
        {
          title: "question2",
          type: "engineer",
          body: "did you love your father?",
          answers: [
            {
              text: "yes",
              value: "yes",
            },
            {
              text: "no",
              value: "no",
            },
          ],
        },
        {
          title: "question3",
          type: "engineer",
          body: "what is your mark in english?",
          answers: [
            {
              text: "50",
              value: "50",
            },
            {
              text: "80",
              value: "80",
            },
            {
              text: "90",
              value: "90",
            },
            {
              text: "20",
              value: "20",
            },
          ],
        },
        {
          title: "question4",
          type: "engineer",
          body: "you love english languge?",
          answers: [
            {
              text: "yes",
              value: "yes",
            },
            {
              text: "no",
              value: "no",
            },
          ],
        },
        {
          title: "question5",
          type: "engineer",
          body: "what is the name of your city?",
          answers: [
            {
              text: "mansora",
              value: "mansora",
            },
            {
              text: "nasr city",
              value: "nasrcity",
            },
          ],
        },
        {
          title: "question6",
          type: "engineer",
          body: "what is your favourite color?",
          answers: [
            {
              text: "red",
              value: "red",
            },
            {
              text: "blue",
              value: "blue",
            },
            {
              text: "green",
              value: "green",
            },
            {
              text: "yellow",
              value: "yellow",
            },
          ],
        },
      ],
      page: 1,
      pageCount: 0,
      itemsPerPage: 1,
      
      pagination: {},
    };
  },

  methods: {
    doSomething(v) {
      console.log("pagination", v);
      this.pagination = v;
    },
  },
};
</script>
<style>
.theme--light.v-label {
  color: #000 !important;
  font-weight: bold;
  padding-left: 5px;
  margin-top: 6px;
}
.subbtn {
  padding-top: 10px !important;
}
</style>

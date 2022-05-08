<template>
  <div>
    <navbar />
    <section class="questions">
      <div class="container">
        <div class="row mt-5">
          <div class="text-center questmain">
            <h1>questions</h1>
          </div>
        </div>
        <!-- <div class="timer">
          <h1>
            {{ timerCount }}
          </h1>
        </div> -->
        <div class="row mt-5">
          <p style="color: #ffffff" class="mt-3 font-weight-bold">
            Current questions: {{ currentPage }} / {{ qunum.length }}
          </p>
          <div
            class="col-md-12"
            :key="index"
            v-for="(item, index) in paginatedItems"
          >
            <div class="question">
              <p>{{ item.body }}</p>
              <div class="answers mt-5">
                <v-radio-group v-model="selectedAnswer" mandatory>
                  <v-row>
                    <v-col v-for="(answer, index) in item.answers" :key="index"
                      ><v-radio
                        :label="answer.text"
                        :value="answer.value"
                        @click="addvalue"
                      ></v-radio
                    ></v-col>
                  </v-row>
                </v-radio-group>
              </div>
            </div>
          </div>

          <div style="width: 100%">
            <b-pagination
              @change="onPageChanged"
              :total-rows="totalRows"
              :per-page="perPage"
              v-model="currentPage"
              prev-text="Prev"
              next-text="Next"
              class="my-0"
            />
          </div>
        </div>
        <div class="navigations">
          <button class="btn quesnav subbtn" @click="postanswer">submit</button>
          <!-- <button role="menuitem" type="button" tabindex="-1" aria-label="Go to previous page" class="page-link">Prev</button> -->
          <nuxt-link to="" class="btn quesnav next-btn mb-3 mt-3"
            >next</nuxt-link
          >
        </div>
        <nuxt-link to="" class="btn quesnav quesprev next-btn mb-3 mt-3"
          >previous</nuxt-link
        >
      </div>
    </section>
  </div>
</template>
<script>
import Navbar from "../components/navbar.vue";

var items = new Array
export default {
  data() {
    return {
      // timerCount: 6000,
      // items: [],
      paginatedItems: items,
      currentPage: 1,
      perPage: 1,
      totalRows: items.length,
      selectedAnswer: [],
      allanswers: [],
      qunum:items
    };
  },
  async fetch() {
    await this.getquestions()
  },
  methods: {
    async getquestions() {

      const questions = this.$axios.get("https://625c1367c9e78a8cb9b36430.mockapi.io/questions")
      items.push(questions)

    },
    paginate(page_size, page_number) {
      let itemsToParse = items;
      this.paginatedItems = itemsToParse.slice(
        page_number * page_size,
        (page_number + 1) * page_size
      );
    },
    addvalue() {
      this.allanswers.push({ answer: this.selectedAnswer });
    },
    async postanswer() {
      const data = {
        //  id:this.selectedAnswer.index,
        allanswers: this.allanswers,
      };
      try {
        
        const res = await this.$axios.post(
          "https://625c1367c9e78a8cb9b36430.mockapi.io/questionsanswer",
          data
        );
        console.log(res);
      } catch (e) {
        console.log(e.message);
      }
    },
    onPageChanged(page) {
      this.paginate(this.perPage, page - 1);
    },
  },
  mounted() {
    this.paginate(this.perPage, 0);
  },

  // watch: {
  //   timerCount: {
  //     handler(value) {
  //       if (value > 0) {
  //         setTimeout(() => {
  //           this.timerCount--;
  //         }, 1000);
  //       }
  //     },
  //     immediate: true, // This ensures the watcher is triggered upon creation
  //   },
  // },
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

<!-- test = [
{
"title": "question1",
"type": "engineer",
"body": "what is your last name?",
"answers": [
{
"text": "kareem",
"value": "kareem"
},
{
"text": "ahmed",
"value": "ahmed"
},
{
"text": "ali",
"value": "ali"
},
{
"text": "omar",
"value": "omar"
}
]
},
{
"title": "question2",
"type": "engineer",
"body": "did you love your father?",
"answers": [
{
"text": "yes",
"value": "yes"
},
{
"text": "no",
"value": "no"
}
]
},
{
"title": "question3",
"type": "engineer",
"body": "what is your mark in english?",
"answers": [
{
"text": "50",
"value": "50"
},
{
"text": "80",
"value": "80"
},
{
"text": "90",
"value": "90"
},
{
"text": "20",
"value": "20"
}
]
},
{
"title": "question4",
"type": "engineer",
"body": "you love english languge?",
"answers": [
{
"text": "yes",
"value": "yes"
},
{
"text": "no",
"value": "no"
}
]
},
{
"title": "question5",
"type": "engineer",
"body": "what is the name of your city?",
"answers": [
{
"text": "mansora",
"value": "mansora"
},
{
"text": "nasr city",
"value": "nasrcity"
}
]
},
{
"title": "question6",
"type": "engineer",
"body": "what is your favourite color?",
"answers": [
{
"text": "red",
"value": "red"
},
{
"text": "blue",
"value": "blue"
},
{
"text": "green",
"value": "green"
},
{
"text": "yellow",
"value": "yellow"
}
]
}
] -->

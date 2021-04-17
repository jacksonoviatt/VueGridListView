<template>
  <div>
    <!-- v-if conditional statement, the button will display if viewAsList is true -->
    <!-- add an event with @click that runs the function gridView, this function toggles  viewAsList true or false  -->
 
    <button v-if="viewAsList === true" @click="gridView">Change to grid</button>
    <button v-else-if="viewAsList === false" @click="listView">Change to list</button>
    <!-- v-bind:class wilk add a class if that variable is true -->
    <section v-bind:class="{viewAsList, viewAsGrid}">
      <!-- a for loop that loops through the tweetlist array, I can then call the key-value pairs in the mustache -->
    <div v-for="string in tweetList" :key="string.object">
      <h4>@{{ string.tweetUser }} said:</h4>
      <p>{{ string.tweetContent }}</p>
      <h6>on: {{ string.tweetedOn }}</h6>
    </div>
    </section>
  </div>
</template>

<script>
export default {
  // name the component
  name: "list-view",
 
// write functions in the methods
  methods: {
    gridView: function() {
      this.viewAsList = false;
      this.viewAsGrid = true;
    },
    listView: function() {
      this.viewAsList = true;
      this.viewAsGrid = false;
    }
  },


  data() {
    return {
      // set the view variables so the page loads as a list
      viewAsList: true,
      viewAsGrid: false,
      // write a variable that holds an array of tweet objects
      testString: "tweetlist yayyy",
      tweetList: [
        {
          tweetContent: "this is the first tweet",
          tweetUser: "userOne",
          tweetedOn: "April 7, 2021",
        },
        {
          tweetContent: "this is the second tweet",
          tweetUser: "userTwo",
          tweetedOn: "February 17, 2021",
        },
        {
          tweetContent: "this is the third tweet",
          tweetUser: "userThree",
          tweetedOn: "January 4, 2021",
        },
         {
          tweetContent: "this is the fourth tweet",
          tweetUser: "userFour",
          tweetedOn: "January 4, 2021",
        },
            {
          tweetContent: "this is the fifth tweet",
          tweetUser: "userFive",
          tweetedOn: "January 4, 2021",
        },
            {
          tweetContent: "this is the sixth tweet",
          tweetUser: "userSix",
          tweetedOn: "January 4, 2021",
        },
            {
          tweetContent: "this is the seventh tweet",
          tweetUser: "userSeven",
          tweetedOn: "January 4, 2021",
        },
            {
          tweetContent: "this is the eigth tweet",
          tweetUser: "userEight",
          tweetedOn: "January 4, 2021",
        },
            {
          tweetContent: "this is the ninth tweet",
          tweetUser: "userNine",
          tweetedOn: "January 4, 2021",
        },
      ],
    };
  },
};
</script>

<style scoped>
.viewAsGrid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
  }
</style>
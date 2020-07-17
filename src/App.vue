<template>
  <div id="app">
    <!-- 1) Hook up the button to toggle the display of the two paragraphs. Use both v-if and v-show and inspect the elements to see the difference -->
    <div>
      <b-button @click="toggleShow">Toggle</b-button>
      <p v-if="showMe">You either see me ...</p>
      <p v-else>...or me</p>
      <p v-show="showMe">You either see me ...</p>
      <p v-show="!showMe">...or me</p>
    </div>
    <!-- 2) Output an <ul> of array elements of your choice. Also print the index of each element. -->
 

    <b-list-group> 
      <b-list-group-item v-for="(obj, index) in array">{{ index }}: {{ obj }} </b-list-group-item>
    </b-list-group>
    <!-- 3) Print all key-value pairs of the following object: {title: 'Lord of the Rings', author: 'J.R.R. Tolkiens', books: '3'}. Also print the index of each item. -->
    <b-card title="Part 3">  
      <b-card-body>
        <b-list-group>
          <b-list-group-item v-for="(val, key, idx) in myObject">
          {{ idx }}.{{ key }}: {{ val }}
          </b-list-group-item>
        </b-list-group> 
      </b-card-body>
    </b-card>

    <!-- 4) Print the following object (only the values) and also create a nested loop for the array: {name: 'TESTOBJECT', data: [1.67, 1.33, 0.98, 2.21]} (hint: use v-for and v-if to achieve this) -->
<b-card>
  <b-card-header>Part 4</b-card-header>
  <b-card-body>
    <b-list-group>
      <b-list-group-item v-for="(item, key) in testData">
        <span v-if="key != 'data'">{{ item }}</span>
        <span v-else>
          DATA:
          <span v-for="i in item">{{ i }}, </span>
        </span>

      </b-list-group-item>
    </b-list-group>
  </b-card-body>
</b-card>



  </div>
</template>

<script>
export default {
  name: "App",
  data: function() {
    return {
      showMe: true,
      array: ["Max", "Anna", "Chris", "Manu"],
      myObject: {
        title: "Lord of the Rings",
        author: "J.R.R. Tolkiens",
        books: "3"
      },
      testData: {
        name: "TESTOBJECT",
        id: 10,
        data: [1.67, 1.33, 0.98, 2.21]
      }
    };
  },
  methods: {
    toggleShow: function() {
      this.showMe = !this.showMe;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 30px;
}
</style>

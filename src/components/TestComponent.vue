<template>
  <div class="app-main-container pretty_container">
    <h1>{{ username }}</h1>
  </div>
</template>

<script>
export default {
  name: "TestComponent",
  props: {
    username: String
  }
};
</script>



<style>
body {

  /* background: #999;
  color: lightseagreen; */
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>



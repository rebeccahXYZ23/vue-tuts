<template>
  <!-- conditional rendering -->
  <div>
    <h2 v-if="num === 5">The number is zero</h2>
    <h2 v-else-if="num > 5">the number is more than five</h2>
    <h2 v-else-if="num < 5">the number is less than five</h2>
    <h2 v-else>not a number but a string</h2>
  </div>
</template>


<script>
export default {
  name: "App",
  data() {
    return {
      num: "hello",
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  display: flex;
  justify-content: center;
  padding: 45px 55px;
}
</style>

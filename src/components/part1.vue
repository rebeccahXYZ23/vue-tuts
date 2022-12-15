<template>
  <!-- text interpolation  or mustache syntax to bind partia text content dynamicaaly update the value-->
  <!-- <div> {{ greet}} {{ name }}</div> -->
  <!-- directives rarely use -->
  <!-- <div v-text="chanel"></div>
 <div v-html="time"></div> -->
  <!-- /<h2 v-bind:id="headingId">Heading</h2>
 <button v-bind:disable="isDisabled">submit</button>
  <h2 class="underline">Underline text</h2> -->
  <h2 class="underline">Danger</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">promoted movies from netflix</h2>
  <h2 v-bind:class="isSoldOut ? 'soldOut' : 'new'">sold-out movies</h2>
  <h2 v-bind:class="['new', 'everyday']">newly promoted movies</h2>
  <!-- array aproach -->
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'soldOut' : 'new']">
    hit Wednesday series
  </h2>
  <!-- object approach -->
  <h2
    v-bind:class="{
      promoted: isPromoted,
      new: !soldOut,
      soldOut: isSoldOut,
    }"
  >
    object conditional movies
  </h2>
  <!-- cased styles -->
  <h2
    :style="{
      color: highlightColor,
      fontSize: headerSize + 'px',
      padding: '20px',
    }"
  >
    inline styles
  </h2>
  <!-- object syntax for multipple codes -->
  <h2 :style="headerStyleObject">Style objects</h2>
  <div :style="[baseStyleObject, successStyleObject]">Success Styles</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      // name: 'everyone',
      // greet: 'hello',
      // chanel: 'netizens',
      // time:' <b> 8:00 pm </b>',
      // headingId: 'heading',
      // isDisabled:false,
      // status:'danger',
      isPromoted: true,
      isSoldOut: true,
      highlightColor: "orange",
      headerSize: 35,
      headerStyleObject: {
        color: "orange",
        fontSize: "25px",
        padding: "5px",
      },
      baseStyleObject: {
        color: "black",
        border: "1px solid green",
        borderRadius: "15px",
      },
      successStyleObject: {
        color: "black",
        "font-weight": 600,
        padding: "15px",
        backgroundColor: "skyblue",
      },
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
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
  font-weight: 500;
}
.new {
  color: aqua;
}
.soldOut {
  color: brown;
}
</style>

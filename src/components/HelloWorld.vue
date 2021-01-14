<template>
  <div class="hello">
    <div v-if="clicked">
      <h1>Your password is weak. Now.</h1>
      Don't ever enter your password into random websites.
    </div>
    <transition name="flip" mode="out-in" :duration="{ enter: 1000, leave: 200 }">
      <div v-if="!clicked">
        <img alt="angel" src="../assets/angel.jpeg">
      </div>
      <div v-else>
        <img src="../assets/hacker.jpeg" alt="hacker">
      </div>
    </transition>
    <h1>{{ msg }}</h1>
    <input v-model="message" placeholder="Enter your password">
    <button v-on:click="clicked = true">Check</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    clicked: Boolean
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

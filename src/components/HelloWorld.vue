<template>
  <div class="hello">
    <div v-if="clicked">

    </div>
    <transition name="fade" mode="out-in">
      <div v-if="clicked" key="hacker">
        <div>
          <h1>Your password is weak. Now.</h1>
          Don't ever enter your password into random websites.
        </div>
        <img src="../assets/hacker.jpeg" alt="hacker">
      </div>
      <div v-if="!clicked" key="angel">
        <img src="../assets/angel.jpeg" alt="angel">
        <h1>{{ msg }}</h1>
        <input v-model="message" placeholder="Enter your password">
        <button v-on:click="clicked = true">Check</button>
      </div>
    </transition>
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
.fade-enter-active {
  transition: opacity 3s;
}
.fade-leave-active {
  transition: opacity 3s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>

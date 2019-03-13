<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <p>{{title}}</p>
    <input type="text" v-on:input="changeTitle">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  data() {
    return {
      title: "Hola caracola"
    };
  },
  methods: {
    changeTitle: function(event) {
      console.log("Event", event);
      this.title = event.target.value;
    }
  },
  components: {
    HelloWorld
  }
};
</script>

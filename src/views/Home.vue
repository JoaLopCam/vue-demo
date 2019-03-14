<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <p>{{title}}</p>
    <p>{{returnInterpolation()}} jiji</p>
    <a v-bind:href="link">Link a google</a>
    <input value="Escucha dos eventos" type="text" v-on="{ input: changeTitle, click: doThat }">
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
      title: "Hola caracola",
      careThis: "Usando this en methods",
      link: "http://google.com"
    };
  },
  methods: {
    changeTitle: function(event) {
      console.log("Event", event);
      this.title = event.target.value;
    },
    doThat: function(event) {
      console.log("Click", event);
    },
    returnInterpolation: function(event) {
      return this.careThis;
    }
  },
  components: {
    HelloWorld
  }
};
</script>

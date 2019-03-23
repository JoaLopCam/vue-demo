<template>
  <div class="home">
    <p v-once>{{title}}</p>
    <p>{{title2}}</p>
    <p>{{returnInterpolation()}} jiji</p>
    <a v-bind:href="link">Link a google</a>
    <input value="Escucha dos eventos" type="text" v-on="{ input: changeTitle, click: doThat }">
    <BasicComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import BasicComponent from "@/components/BasicComponent.vue";

export default {
  name: "home",
  data() {
    return {
      title: "Tiene v-once no se modificara",
      title2: "Se modificara dependiendo del valor del input",
      careThis: "Usando this en methods",
      link: "http://google.com"
    };
  },
  methods: {
    changeTitle: function(event) {
      console.log("Event", event);
      this.title = event.target.value;
      this.title2 = event.target.value;
    },
    doThat: function(event) {
      console.log("Click", event);
    },
    returnInterpolation: function(event) {
      return this.careThis;
    }
  },
  components: {
    BasicComponent
  }
};
</script>

<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div>
      <input type="text" @input="inputchange" v-model="inputdata" />
    </div>
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import _ from "lodash";
export default defineComponent({
  name: "Home",
  components: {
    HelloWorld
  },
  setup() {
    const inputdata = ref("");
    const inputchange = _.debounce(function() {
      console.log("value", inputdata.value);
    }, 1000);
    return {
      inputchange,
      inputdata
    };
  }
});
</script>

<template>
  <v-switch :case="name1">
    <template #one>one</template>
    <template #two>two</template>
    <template #three>three</template>
    <template #default>default</template>
  </v-switch>
  <p>当前的name1-,{{name1}}</p>
  <button @click="click">name1</button>
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";
import vSwitch from "./components/v-switch.vue";

export default defineComponent({
  name: "App",
  components: {
    vSwitch,
  },
  setup() {
    let count = 1;
    const name1 = ref('one');

    const click = () => {
      count++;
      name1.value = count % 3 === 0 ? "one": count % 3 === 1 ? "two": "three"
    };
    return {
      name1,
      click,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

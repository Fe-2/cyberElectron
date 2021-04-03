<template>
  <h1>{{a.b}}</h1>
</template>

<script>
import {
  reactive,
  ref,
  toRef,
 unref,
 isProxy,
  } from 'vue';

export default {
  name: 'App',
  setup() {
    const count = ref({
      a: {
        b:1
      }
    });
    const s = toRef(count, "a");
    console.log(s.value);
    setTimeout(()=>{
      count.a.b = 3232;
    },2000);
    return {
      ...count
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin: 60px;
}
</style>
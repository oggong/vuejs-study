<template>
  <div id="app">
     <p>{{ person1.name }} {{ person1.value }}</p>
    <button @click="handleClick">click</button>
  </div>
</template>

<script>

import { ref, reactive } from "vue";

export default {
  name: 'App',
  setup() {
    // 데이터를 ref, reactive로 감싸면 반응형으로 바뀝니다.
    const person1 = ref({ name: "nkh", age: 29 });
    const person2 = reactive({ name: "nki", age: 26 });

    const handleClick = () => {
      // ref로 감싼 값을 변경할 때는 value로 한번 들어가주고 값을 바꿉니다.
      person1.value.age = 30;

      // reactive는 바로 값을 바꿉니다.
      person2.age = 30;
    };

    return { person1, handleClick };
  }
}
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

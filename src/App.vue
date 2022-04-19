<template>
  <div id="app">
    <div class="container">
      <h2>TODO LIST</h2>
      <TodoList />
    </div>
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    TodoList,
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  font-size: 18px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-image: url("./assets/background.png");
  background-repeat: no-repeat;
  background-size: 100% 500px;
  height: 100vh;
}

.container {
  padding-top: 300px;
  width: 600px;
}

h2 {
  text-align: center;
  color: cornsilk;
  text-shadow: 2px 2px rgba(0, 0, 0, 0.2);
}
</style>

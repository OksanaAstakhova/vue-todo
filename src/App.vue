<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>To Do List From Oksana Astakhova</h1>
    <br>
     <!-- <AddDo v-on:add-todo="addTodo" />
    <ToDoList v-bind:todos = "todos" v-on:remove-todo="removeTodo" /> -->
    <router-view />
  </div>
</template>

<style>
  body {
  height: auto;
  background: linear-gradient(#414d59, #b1bfc1) no-repeat;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #8dacb6;
  margin-top: 10px;
}
a {
  text-decoration: none;
  color: #5a7980;
  font-size: 22px;
}
img {
  width: 80px;
  height: auto;
}
h1 {
  border-bottom: 1px solid #3d493d;
  font-size: 24px;
  padding-bottom: 10px;
  color: #8dacb6;
  border-bottom: 1px solid #ecf1ec;
}
p {
  color: #5a7980;

}

</style>

<template>
  <div>
      <router-link to="/">Home page</router-link>
     <AddDo v-on:add-todo="addTodo" />
    <ToDoList v-bind:todos = "todos" v-on:remove-todo="removeTodo" />
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";
import AddDo from "@/components/AddDo";

export default {
  name: 'App',
  data() {
    return {
      todos: [
        // { id: 1, title: "Learn JavaScript", completed: false},
        // { id: 2, title: "Learn Vue JS", completed: false},
        // { id: 3, title: "Pass Exam", completed: false},
        // { id: 4, title: "Relax After Exam", completed: false},
      ]
    }
  },
  mounted() { // для роботи з сервером 
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=10') // ?_limit=10 написали самі для обмеження кількості
  .then(response => response.json())
  .then(json => {
    this.todos = json;
  });
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
    }
  },
  components: {
    ToDoList,
    AddDo  
  }
}
</script>

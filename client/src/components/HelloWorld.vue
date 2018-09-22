<template>
  <div>
    <h1>Hello Todos</h1>
    <form v-on:submit="addTask">
      <input type="text" v-model="todos.name">
      <input  type="submit" value="Add">
    </form>

    <div v-for="todo in todos">
      <div>{{todo.name}}  <button v-on:click="deleteTask(todo)">&times;</button></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      todos: [
        {name: 'Koupit pečivo', done: false},
        {name: 'Jít si zaběhat', done: false},
        {name: 'Podívat se na oblíbený film/seriál', done: false},
      ]
    }
  },
  methods: {
    addTask(e){
      e.preventDefault();
      this.todos.push({
        name: this.todos.name,
        done: false
      });
    },
    deleteTask(todo){
      this.todos.splice(this.todos.indexOf(todo), 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

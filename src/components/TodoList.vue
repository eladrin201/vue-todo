<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <ul id="todos">
      <todo v-on:delete-todo="deleteTodo" v-bind:todo="todo" v-for="(todo, k) in todos" :key="k"></todo>
    </ul>
  </div>
</template>

<script type="text/javascript">
import Todo from './Todo';

export default {
  props: ['todos'],
  events: ['delete-todo'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo: function(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    }
  }
};
</script>

<style media="screen">
h2 small {
  display: block;
}
</style>

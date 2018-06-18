<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <ul id="todos">
      <todo v-for="(todo, key) in todos" :key="key"  v-bind:todo="todo"></todo>
    </ul>
  </div>
</template>

<script type="text/javascript">
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
};
</script>

<style media="screen">
h2 small {
  display: block;
}
</style>

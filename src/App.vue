<template>
  <todo-list v-bind:todos="todos"></todo-list>
</template>

<script type ="text/javascript">
import TodoList from './components/TodoList';
import Todo from './components/Todo';

export default {
  name: 'app',
  components: {
    TodoList,
    Todo,
  },
  data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
};
</script>

<style>
  /* Global styles */
  .sr-only {
    position:absolute;
    left:-10000px;
    top:auto;
    width:1px;
    height:1px;
    overflow:hidden;
  }
</style>

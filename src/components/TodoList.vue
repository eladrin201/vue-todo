<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <ul id="todos">
      <li class="ui centered card" v-for="(todo, key) in todos" :key="key" v-if="todo">
        <div class="content">
          <h2 class="header">
            {{ todo.title }}
            <small>
              {{ todo.project }}
            </small>
          </h2>
          <div class="extra content">
            <button class="right floated edit icon">
              <i class="edit icon"></i>
              <span class="sr-only">Edit</span>
            </button>
            <button class="ui bottom attached green basic button" v-show="todo.done">
              Completed
            </button>
            <button class="ui bottom attached red basic button" v-show="!todo.done">
              Complete
            </button>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script type="text/javascript">
export default {
  props: ['todos'],
};
</script>

<style media="screen">
  h2 small {
    display: block;
  }
</style>

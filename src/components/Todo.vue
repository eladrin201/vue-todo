<template lang="html">
  <li class="ui centered card" v-if="todo">
    <div class="content" v-show="!isEditing">
      <h2 class="header">
        {{ todo.title }}
      </h2>
      <p class="meta">
        {{ todo.project }}
      </p>
    </div>
    <div class="content" v-show="isEditing">
      <form class="ui form">
        <div class='field'>
          <label>Title
            <input type='text' v-model="todo.title">
          </label>
        </div>
        <div class="field">
          <label>Project Details
            <input type="text" v-model="todo.project">
          </label>
        </div>
        <div class='ui two button attached buttons'>
          <button class='ui basic blue button' v-on:click="hideForm">
            Save
          </button>
        </div>
      </form>
    </div>
    <div class="extra content">
      <button class="right floated edit icon" v-on:click="showForm">
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
  </li>
</template>

<script type="text/javascript">
export default {
  props: ['todo'],
  data() {
    return {
      isEditing: false,
    };
  },
  methods: {
    showForm() {
      this.isEditing = true;
    },
    hideForm() {
      this.isEditing = false;
    },
  },
};
</script>

<style lang="css">
</style>

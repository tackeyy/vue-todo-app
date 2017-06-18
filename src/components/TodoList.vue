<template>
  <div>
    <p class="tasks">完了したタスク: {{ todos.filter(todo => { return todo.done === true }).length }}</p>
    <p class="tasks">未完了のタスク: {{ todos.filter(todo => { return todo.done === false }).length}}</p>
    <div class='ui centered card' v-for="todo in todos">
      <div class='content'>
        <div class='header'>
          {{ todo.title }}
        </div>
        <div class='meta'>
          {{ todo.project }}
        </div>
        <div class='extra content'>
          <span class='right floated edit icon'>
            <i class='edit icon'></i>
          </span>
        </div>
        <div class='ui bottom attached green basic button' v-show="todo.done">
          Completed
        </div>
        <div class='ui bottom attached red basic button' v-show="!todo.done">
          Complete
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['todos']
}
</script>

<style>
.tasks {
  text-align: center;
}
</style>

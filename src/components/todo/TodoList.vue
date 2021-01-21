<template>
  <div class="todo-list">
    <div v-for="todo in todos" :key="todo.id">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
  name: 'TodoList',
  props: {
    todos: Array
  },
  components: {
    TodoItem
  }
}
</script>

<style lang="scss" scoped>
.todo-list {
  margin-top: 2rem;
}
</style>

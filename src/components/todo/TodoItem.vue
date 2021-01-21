<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
    <label @click="markComplete">
      <input type="checkbox" v-bind:id="todo.id" @change="markComplete" :checked="todo.completed" />
      {{ todo.title }}
    </label>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: Object
  },
  methods: {
    markComplete () {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style lang="scss" scoped>
.todo-item {
  border-bottom: 1px solid #e5e5e5;
  padding: .5rem;
  margin-bottom: .5rem;
  &.is-complete {
    text-decoration: line-through;
  }
  label {
    width: 100%;
    display: block;
    margin-left: -1.2rem;
    &:hover {
      cursor: pointer;
    }
  }
}
</style>

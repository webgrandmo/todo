<template>
  <div>
    <form @submit.prevent="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
      />
      <button type="submit" value="Submit" class="btn">
        <i>
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill-rule="evenodd" d="M11.75 4.5a.75.75 0 01.75.75V11h5.75a.75.75 0 010 1.5H12.5v5.75a.75.75 0 01-1.5 0V12.5H5.25a.75.75 0 010-1.5H11V5.25a.75.75 0 01.75-.75z"></path></svg>
        </i>
      </button>
    </form>
  </div>
</template>

<script>
import { v4 } from 'uuid'
export default {
  name: 'AddTodo',
  data () {
    return {
      title: ''
    }
  },
  methods: {
    addTodo () {
      const newTodo = {
        id: v4(),
        title: this.title,
        completed: false
      }
      // Send up to parent
      this.$emit('add-todo', newTodo)

      this.title = ''
    }
  }
}
</script>

<style lang="scss" scoped>
form {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #e5e5e5;
  input {
    border: none;
    border-radius: 0;
    outline: none;
    padding: 0.25rem 0;
    width: 100%;
    font-size: 1rem;
    line-height: 1.5rem;
    flex-grow: 2;
  }
  button {
    flex-grow: 1;
    border: none;
    background: none;
    outline: none;
    cursor: pointer;
  }

  svg {
    width: 1rem;
    height: 1rem;
    fill: #ccc;
    transition: transform 0.1s ease-out;
  }

}
</style>

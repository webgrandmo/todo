<template>
  <section class="date-container">
    <header>
      <h1 class="day-of-week">Monday</h1>
      <p class="full-date">January 21th 2021</p>
    </header>
    <TodoList v-bind:todos="todos" />
    <AddTodo v-on:add-todo="addTodo($event)" />
  </section>
</template>

<script>
import TodoList from './components/todo/TodoList'
import AddTodo from './components/todo/AddTodo'

export default {
  name: 'App',
  components: {
    TodoList,
    AddTodo
  },
  data () {
    return {
      todos: [
        {
          id: 1,
          title: 'Todo One',
          completed: false
        },
        {
          id: 2,
          title: 'Todo Two',
          completed: false
        },
        {
          id: 3,
          title: 'Todo Three',
          completed: false
        }
      ]
    }
  },
  methods: {
    addTodo (newTodo) {
      if (newTodo.title.trim()) {
        this.todos = [...this.todos, newTodo]
      }
      console.log(this.todos)
    }
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Roboto, Helvetica, Arial, sans-serif;
}
body {
  padding: 1rem 2rem;
}
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;700&display=swap');
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 1rem;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

p {
  margin-top: 0.5rem;
}
  .date-container {
    width: 100%;
    margin: 0 auto;
    @media screen and (min-width: 40rem) {
      width: 45%;
    }
    @media screen and (min-width: 40rem) {
      width: 25%;
    }

    header {
      text-align: center;
      text-transform: uppercase;
      h1 {
        font-size: 1.5rem;
      }

      p {
        font-size: .8rem;
        font-weight: 300;
        color: #999;
      }
    }
  }
</style>

<style lang="scss" scoped>

</style>

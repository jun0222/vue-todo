<script>
export default {
  methods: {},
  data() {
    return {
      todos: [
        {
          id: 1,
          isDone: true,
          text: 'Vueをマスターする'
        },
        {
          id: 2,
          isDone: false,
          text: '牛乳を買う'
        },
        {
          id: 3,
          isDone: false,
          text: '家賃を払う'
        }
      ]
    }
  }
}
</script>

<template>
  <h1>My ToDo App</h1>
  <input type="text" /><button>追加</button><button>完了済みを削除する</button>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      <input type="checkbox" /><span>{{ todo.text }}</span>
    </li>
  </ul>
</template>

<style>
body {
  background-color: #eee;
}

.todo-done {
  text-decoration: line-through;
}
</style>

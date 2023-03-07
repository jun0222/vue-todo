<script>
export default {
  data() {
    return {
      newTodoText: '',
      todos: []
    }
  },
  methods: {
    addTodo() {
      if (!this.newTodoText) return alert('文字を入力してください')
      this.todos.push({
        isDone: false,
        text: this.newTodoText
      }),
        (this.newTodoText = '')
    },
    clearDoneTodos() {
      this.todos = this.todos.filter((todo) => !todo.isDone)
    }
  }
}
</script>

<template>
  <h1>My ToDo App</h1>
  <input type="text" v-model="newTodoText" /><button @click="addTodo">追加</button>
  <button @click="clearDoneTodos">完了済みを削除する</button>
  <p v-if="todos.length === 0">ToDoがまだありません！</p>
  <ul v-else>
    <li v-for="todo in todos" :key="todo.id">
      <input type="checkbox" v-model="todo.isDone" /><span :class="{ 'todo-done': todo.isDone }">{{
        todo.text
      }}</span>
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

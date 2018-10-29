<template>
  <div id="addTodo">
    <input
      type="text"
      v-model="newTodoText"
      placeholder="New todo"
      class="input"
      value="回车确认"
      @keyup.enter="addTodo"
    >
    <todoListItem
      @remove="removeTodo"
      @finish="finish"
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      :flag="todo.flag"
    />
  </div>
</template>

<script>
import todoListItem from './todoListItem.vue'
var nextTodoId = 1
export default {
  name: 'todoInput',
  components: {
    todoListItem
  },
  data () {
    return {
      newTodoText: '',
      todos: [
        {
          id: nextTodoId++,
          text: '考试啊',
          flag: true
        }
      ]
    }
  },
  methods: {
    addTodo () {
      const trimmedText = this.newTodoText.trim()
      if (trimmedText) {
        this.todos.push({
          id: nextTodoId++,
          text: trimmedText,
          flag: true
        })
        this.newTodoText = ''
      }
    },
    removeTodo (idToRemove) {
      this.todos = this.todos.filter(todo => {
        return todo.id !== idToRemove
      })
    },
    finish (flag, id) {
      this.todos[id - 1].flag = !flag
    }
  }
}
</script>

<style scoped>
.input{
  width:60%;
  height:30px;
  padding:5px 10px;
  left:20%;
  border-color: #cbced6;
  border-radius: 10px;
}
</style>

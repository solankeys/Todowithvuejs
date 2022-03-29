<template>
<div class="todo container">
  <!-- <h1>Todo List</h1>
   -->
   <h1>{{title}}</h1>
  <div class="todo__form">
    <input type="text" class="todo__formcontrol" v-model="todoName" @keyup.enter="addTodos" placeholder="Enter Your Todo">
    <button class="todo__btn" @click="addTodos">Add</button>
  </div>
  <div class="todos">
    <ul>
    <li v-for='(todo, index) in todos' :key='index'><span>{{todo.todo}}</span><button class="delete" @click="deleteTodo(todo.id)">Delete</button></li>
    </ul>
  </div>
  <button class=" delete deleteAll" @click="deleteAllTodo">Delete All</button>
</div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'ToDo'
}
</script>
<script setup>
const title = ref('Todo')
const todoName = ref('')
const todos = ref([])

const addTodos = () => {
  if (!todoName.value) {
    alert('Please fill the field')
  } else {
    const todo = {
      id: Date.now().toString(),
      todo: todoName.value
    }
    todos.value.push(todo)
    todoName.value = ''
  }
}

const deleteTodo = (id) => {
  const newTodo = todos.value.filter((item) => item.id !== id)
  todos.value = newTodo
}

const deleteAllTodo = () => {
  todos.value = []
}

</script>

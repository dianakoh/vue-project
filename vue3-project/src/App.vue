<template>
  <div class="container">
    <h2>To-Do List</h2>
    <TodoSimpleForm @add-todo="addTodo"/>

    <div v-if="!todos.length">
      추가된 Todo가 없습니다
    </div>
    <TodoList :todos="todos" />
  </div>
</template>

<script>
import {ref} from 'vue';
import TodoSimpleForm from './components/TodoSimpleForm.vue';
import TodoList from "./components/TodoList.vue";

export default {
  components: {
    TodoSimpleForm,
    TodoList
  },
  setup() {

    const todos = ref([]);
    
    const todoStyle = {
      textDecoration: 'line-through',
      color: 'gray'
    };

    const addTodo = (todo) => {
      todos.value.push(todo);
    };

    const deleteTodo = (index) => {
      todos.value.splice(index, 1);
    };

    return  {
      todos,
      todoStyle,
      deleteTodo,
      addTodo
    };
  },
}
</script>

<style scoped>
  .todo {
    color: gray;
    text-decoration: line-through;
  }
</style>
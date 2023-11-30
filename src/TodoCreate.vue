<template>
  <form 
    class="todo__items" 
    @submit.prevent="addTodo"
  >
    <div class="todo__item">
      <input 
        v-model="text"
        type="text"
        class="todo__input"
        placeholder="Оставте заметку"
      >

      <button 
        type="submit" 
        class="todo__button"
      >
        Добавить
      </button>
    </div>
  </form>

  <ul>
    <TodoList 
      v-for="todo in todos" 
      :key="todo.id" 
    />
  </ul>
</template>

<script>
import TodoList from './TodoList.vue'
let id = 0;
export default {
  data() {
    return {
      text: '',
      todos: [],
    }
  },
  methods: {
    addTodo() { // функция добавление по клику на кнопку добавить
      if (this.text) {
        this.todos.push({id: id++, text: this.text, done: false}) // Добавление обьекта с id и текстом в массив todos
        this.text = '' // после ввода текста в инпут, очищаем его
      }
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((item) => item !== todo)
    }
  },
}
</script>

<style>
  .todo__item {
    display: flex;
    align-items: center;
    gap: 10px;
  }
.todo__input {
    font-size: 24px;
    line-height: 30px;
    font-weight: 400;
    padding: 12px 20px;
    color: #000;
    background-color: transparent;
    border: 1px solid #807777;
    border-radius: 6px;
    max-width: 400px;
    width: 100%;
    outline-color: rgb(68, 68, 190);
  }
  .todo__button {
    font-size: 24px;
    line-height: 30px;
    font-weight: 400;
    color: #000;
    background-color: transparent;
    border: 1px solid #807777;
    border-radius: 10px;
    padding: 12px;
    cursor: pointer;
    transition: color 0.3s ease-in-out, border 0.3s ease-in-out;
  }
  .todo__button:hover {
    color: rgb(68, 68, 190);
    border-color: rgb(68, 68, 190);
  }
</style>
<template>
  <div class="container">
    <div class="todo">
      <h1 class="title"> 
        {{ title }}
      </h1>

      <form 
        action="#"
        @submit.prevent="addTodo"
      >
        <div class="todo__item">
          <TodoInput />
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import TodoInput from './TodoInput.vue'
// import TodoAdd from './TodoAdd.vue'

export default {
  components: {
    TodoInput,
    // TodoAdd,
  },
  data() {
    return {
      title: 'Ваши заметки',
    }
  },
  methods: {
    
  }
}
</script>

<style>
.container {
    display: flex;
    justify-content: center;
    max-width: 1200px;
    height: 300px;
    margin: 0 auto;
  }
  .title {
    font-size: 38px;
    color: #000;
    margin: 0 0 50px 0;
    text-align: center;
  }
  .todo__item {
    display: flex;
    align-items: center;
    gap: 10px;
  }
</style>

<!-- <template>
  <div class="container">
    <div class="todo">
      <h1 class="title">
        {{ title }}
      </h1>

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

        <ul>
          <li 
            v-for="todo in todos" 
            :key="todo.id" 
            class="todo-list__content"
          >
            <div class="todo-list__group">
              <div class="todo-list__item">
                <input 
                  v-model="todo.done"
                  type="checkbox"
                  class="todo-list__checkbox"
                >
                <span :class="{ done: todo.done }">{{ todo.text }}</span>
              </div>

              <div class="todo-list__item">
                <button 
                  type="button" 
                  class="todo-list__button" 
                  @click="removeTodo(todo)"
                >
                  Удалить заметку
                </button>
              </div>
            </div>
          </li>
        </ul>
      </form>
    </div>
  </div>
</template>

<script>
import TodoInput from './TodoInput.vue'

let id = 0;

export default {
  components: {
    TodoInput
  },
  data() {
    return {
      title: 'Ваши заметки', // Заголовок
      text: '', // Значение с инпута
      todos: [] // пустой массив, куда будет добавляться текс и id
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
  .container {
    display: flex;
    justify-content: center;
    max-width: 1200px;
    height: 300px;
    margin: 0 auto;
  }
  .title {
    font-size: 38px;
    color: #000;
    margin: 0 0 50px 0;
    text-align: center;
  }
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

  .todo-list__content:not(:last-child) {
    margin-bottom: 20px
  }
  .todo-list__group {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
  }
  .todo-list__item {
  
  }
  .todo-list__checkbox {
    width: 18px;
    height: 18px;
    margin-right: 6px;
  }
  .done {
  text-decoration: line-through;
}
  .todo-list__item span {
    font-size: 24px;
    font-weight: 500;
    color: #000;
  }
  .todo-list__button {
    padding: 10px;
    font-size: 20px;
    line-height: 24px;
    font-weight: 400;
    color: #000;
    background-color: transparent;
    border: 1px solid #807777;
    border-radius: 10px;
    cursor: pointer;
    transition: color 0.3s ease-in-out, border 0.3s ease-in-out;
  }
  .todo-list__button:hover {
    color: rgb(68, 68, 190);
    border-color: rgb(68, 68, 190);
  }
</style> -->

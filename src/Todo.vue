<template>
  <div class="container">
      <div class="todo">
        <h1 class="title"> {{ title }} </h1>
        <div class="todo__items">
          <div class="todo__item">
            <input v-model="text" type="text" class="todo__input" placeholder="Оставте заметку">
            <button @click="addTodo" class="todo__button">Добавить</button>
          </div>

          <ul>
            <li v-for="todo in todos" :key="todo.id" class="todo-list__item">
              <div class="todo-list__row">
                <span>{{ todo.text }}</span>
                <button @click="removeTodo(todo)" class="todo-list__button">Удалить заметку</button>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
</template>

<script>
let id = 0;

export default {
  data() {
    return {
      title: 'Ваши заметки', // Заголовок
      text: '', // Значение с инпута
      todos: [] // пустой массив, куда будет добавляться текс и id
    }
  },
  methods: {
    addTodo() { // функция добавление по клику на кнопку добавить
      this.todos.push({id: id++, text: this.text}) // Добавление обьекта с id и текстом в массив todos
      this.text = '' // после ввода текста в инпут, очищаем его
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
    align-items: center;
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


  .todo-list__item:not(:last-child) {
    margin-bottom: 20px
  }
  .todo-list__row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
  }
  .todo-list__row span {
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
</style>

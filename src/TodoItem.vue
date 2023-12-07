<template>
  <li class="todo-list__content">
    <div class="todo-list__group">
      <div class="todo-list__item">
        <input 
          :checked="todo.done"
          type="checkbox"
          class="todo-list__checkbox"
          @change="$emit('checked', $event.target.checked)"
        >
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
      </div>

      <div class="todo-list__item">
        <button 
          type="button" 
          class="todo-list__button" 
          @click="$emit('remove')"
        >
          Удалить заметку
        </button>
      </div>
    </div>
  </li>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  props: {
    todo: {
      type: Object,
      required: true,
    }
  },
  emits: ['remove', 'checked'],
  data() {
    return {
      
    }
  },
  methods: {
    
  },
})

</script>

<style scoped>
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
</style>
<template>
  <li class="todo-list__content">
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
          @click="$emit('removeTodo(todo)')"
        >
          Удалить заметку
        </button>
      </div>
    </div>
  </li>
</template>

<script>

export default {
  data() {
    return {
      props: ["todo"],
      emits: ['todo', 'removeTodo(todo)']
    }
  },
  methods: {
    
  },
}
</script>

<style>

</style>
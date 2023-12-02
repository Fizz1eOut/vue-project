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
  // data() {
  //   return {
      
  //   }
  // },
  // methods: {
    
  // },
})

</script>

<style>

</style>
<template>
  <div>
    <TodoListItem
      v-for="todo in todos" 
      :key="todo.id"
      :todo="todo"
    />
    <p>{{ index }}</p>
  </div>
</template>

<script>
import TodoListItem from '@/components/TodoListItem.vue'

export default {
  name: 'TodoList',
  props: {
    todos:Object
  },
  components: {
    TodoListItem,
  },
}
</script>

<style>

</style>
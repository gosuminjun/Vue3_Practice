<template>
  <div>
    <h1>모든 할일</h1>
    <TodoCreateForm/>
    <hr>
    <TodoList
      :todos="todos"
    />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList.vue'
import TodoCreateForm from '@/components/TodoCreateForm.vue'

export default {
  name: 'AllTodoPage',
  components: {
    TodoList,
    TodoCreateForm
  },
  computed: {
    todos() {
      return this.$store.state.list
    }
  }
}
</script>

<style>

</style>
<template>
  <div>
    <h1>중요 할일</h1>
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
  name: 'ImportantTodoPage',
  components: {
    TodoList,
    TodoCreateForm
  },
  computed: {
    todos() {
      const importantTodo = this.$store.state.list.filter((todo) => {
        return todo.isImportant && !todo.isCompleted
      })
      return importantTodo
    }
  }
}
</script>

<style>

</style>
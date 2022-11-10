<template>
  <div>
    <div class @click="toggleEditMode">
      <label>
        <input type="checkbox" class="me-3 d-none" :checked="todo.isCompleted" @change="toggleCompleted">
        <i v-if="todo.isCompleted" class="bi bi-check-circle text-success h4 clickable"></i>   
        <i v-else class="bi bi-circle h4 clickable"></i>   
        <span class="ms-2 clickable">
          {{ todo.content }}
        </span>
      </label>
      <button class="btn ms-auto" @click.stop="toggleImportant">
      <i v-if="todo.isImportant" class="bi bi-star-fill fc-yellow"></i>
      <i v-else class="bi bi-star fc-yellow"></i>
      </button>
    </div>
    <div v-if="editMode">
      <TodoUpdateForm :todo="todo" @toggle-edit-mode="toggleEditMode"/>
    </div>
  </div>
</template>

<script>
import TodoUpdateForm from './TodoUpdateForm.vue'

export default {
  name: 'TodoListItem',
  components: {
    TodoUpdateForm,
  },
  props: {
    todo: Object
  },
  data() {
    return {
      editMode: false,
    }
  },
  methods: {
    toggleCompleted() {
      const data = {
        ...this.todo,
        isCompleted: !this.todo.isCompleted
      }
      this.$store.commit('UPDATE_TODO', data)
      console.log(data)

    },
    toggleImportant() {
      const data = {
        ...this.todo,
        isImportant: !this.todo.isImportant
      }
      this.$store.commit('UPDATE_TODO', data)
    },
    toggleEditMode() {
      this.editMode = !this.editMode
    }
  },
  computed: {
    content() {
      return this.todo.content
    },
    isCompleted() {
      return this.todo.isCompleted
    },
    isImportant() {
      return this.todo.isImportant
    }
  },
}
</script>

<style>

</style>
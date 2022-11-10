<template>
  <div>
    <button>+</button>

    <input 
      type="text" 
      placeholder="할 일을 작성해주세요!"
      v-model="newTodo"
      @keyup.enter = "createTodo"
    >

  </div>
</template>

<script>
export default {
  name: 'TodoCreateForm',
  data() {
    return {
      newTodo: null,
    }
  },
  methods: {
    createTodo() {
      if (this.newTodo) {
        this.$store.commit('CREATE_TODO', this.newTodo)
      }
      this.newTodo = null
    }
  }
}
</script>

<style>

</style>
<template>
  <div id="sidebar">
    <h1>네비게이션 바</h1>
    <router-link to="/">모든</router-link>
    <router-link to="/todaytodopage">오늘</router-link>
    <router-link to="/importanttodopage">중요</router-link>    
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  props: {

  },
}
</script>

<style>
  #sidebar {
  border-radius: .5rem;
  border: 2px solid #2c3e50;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
  /* height: 100vh; */
}
</style>
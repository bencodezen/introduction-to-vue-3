<template>
  <h1>TodoMVC</h1>
  <input
    class="user-input"
    placeholder="What do you want to do?"
    type="text"
    v-model="userInput"
    @keyup.enter="registerTask"
  />
  <form @submit.prevent></form>
  <ul>
    <li v-for="(task, index) in taskList" :key="index">
      {{ task }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      userInput: '',
      taskList: [1, 2, 3]
    }
  },
  methods: {
    registerTask() {
      this.taskList.push(this.userInput)
      this.userInput = ''
    }
  }
}
</script>

<style>
.user-input {
  padding: 1rem;
  font-size: 1.2rem;
  width: 80%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

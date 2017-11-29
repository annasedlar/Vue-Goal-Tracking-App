<template>
  <div id="app">
    <img src="./assets/logo.png">
    <GoalForm v-on:addGoal="addGoal"></GoalForm>
    <List v-bind:goals="goals"></List>
  </div>
</template>

<script>
import GoalForm from '@/components/GoalForm'
import List from '@/components/List'

export default {
  name: 'app',
  components: {
    GoalForm: GoalForm,
    List: List
  },
  data() {
    return(
      {
        goals: ['first goal', 'second goal'] 
      }
    )
  },
  methods: {
    addGoal ({ goalName }) {
      console.log('addGoal function', { goalName })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

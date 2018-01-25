
<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!--   // v-on:TESTING will not run -->
    <GoalForm v-on:addGoal="addGoal" v-on:TESTING="testEmit()"></GoalForm>
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
        goals: [{title:'first goal', done: false}, {title: 'second goal', done: true}] 
      }
    )
  },
  methods: {
    addGoal (newGoal) {
      console.log('this is the parent', newGoal.title)
      this.goals.push(newGoal);
    },
    testEmit(paramsFromGrandChild){
      // This will never run because no more $dispatch in V2 meaning only direct parent component can listen to child events
          console.log("event emitted from grand-child. The status of the child-goal you clicked on: " + params.status)

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

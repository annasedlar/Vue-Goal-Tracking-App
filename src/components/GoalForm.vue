<template>
  <div class="goalInput">
    <h1>{{ msg }}</h1>
    <form>
        <input v-model="goalName" type="text" placeholder="What's your goal?"></input>
        <input type="submit" @click="submit()"></input>
    </form>
  </div>
</template>

<script>
export default {
  name: 'GoalForm',
  data () {
    return {
      msg: 'Welcome to the Goal Tracker App!',
      goalName: '',
    }
  },
  methods: {
    submit() {
      this.$emit('addGoal', {
        title: this.goalName,
        done: false,
      }) 
    }
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.goalInput{
  margin-bottom:20px;
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

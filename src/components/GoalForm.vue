<template>
  <div class="card">
    <h1>{{ msg }}</h1>
    <form>
        <input v-model="goalName" type="text" placeholder="What's your goal?"></input>
        <input type="submit" v-on:click="submit()"></input>
    </form>
  </div>
</template>

<script>
export default {
  name: 'GoalForm',
  data () {
    return {
      msg: 'Welcome to the Goal Tracker App!'
    }
  },
  methods: {
    submit() {
      this.$emit('addGoal', {
        goalName: this.goalName
      }) 
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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

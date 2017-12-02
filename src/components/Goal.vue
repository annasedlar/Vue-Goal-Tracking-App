<template>
    <div v-bind:class="{FinishedGoal: goal.done, IncompleteGoal: !goal.done}">
        <p v-on:click="changeStatus()">
             <span v-show="goal.done">X</span>
            {{goal.title}}
        </p>
    </div>
</template>

<script>
export default {
  name: 'Goal',
  props: ["goal"],
  methods:{
      changeStatus(){
          console.log("changed done")
              this.goal.done = !this.goal.done;
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
.FinishedGoal{
    color: blue
}

.IncompleteGoal{
    color: red
}
</style>

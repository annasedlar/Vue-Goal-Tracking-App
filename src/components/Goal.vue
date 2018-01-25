<template>
    <div :class="{FinishedGoal: goal.done, IncompleteGoal: !goal.done}">
        <p @click="changeStatus(), testFunction()">
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
            console.log("changed status")
                this.goal.done = !this.goal.done;
        },
        testFunction(){
            let status = this.goal.done
            this.$emit('TESTING', {
                status
            })
            console.log("emitting")
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

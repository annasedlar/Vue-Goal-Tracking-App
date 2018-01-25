<template>
  <div class="list">
      <div>{{title}}</div>
      <Goal v-for="goal in goals" :goal="goal" v-on:TESTING="seeEvent"></Goal>
  </div>
</template>

<script>
import Goal from '@/components/Goal'

export default {
  name: 'List',
  props: ["goals"],
  components: {
      Goal
  },
  data () {
    return {
      msg: 'Welcome to the Goal Tracker App!',
      title: this.title
    }
  },
  methods: {
      seeEvent({status}) {
          console.log("event emitted from child. The status of the child-goal you clicked on: " + status)
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.list{
    padding-top:20px;
    margin:auto;
    width: 66%;
    border-top: 1px solid grey; 
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: circle;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  list-style-type: circle;
}
a {
  color: #42b983;
}
</style>

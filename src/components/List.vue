<template>
  <div class="list">
      <Goal v-for="goal in goals" v-bind:goal="goal"></Goal>
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
      msg: 'Welcome to the Goal Tracker App!'
    }
  },
  methods: {
      submit() {
          console.log("new goal submitted")
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

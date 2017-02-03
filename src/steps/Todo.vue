<template>
  <div class="to-do">
    <ol>
      <h1>My todo list</h1>
      <div v-for='task in tasks' style="margin-bottom: 10px;" class="clear">
        <li style="float:left" v-bind:class="{checked: task.completed}">{{task.name}}</li>
        <input type="checkbox" v-model="task.completed" style="float:left">
      </div>
    </ul>
    <br>
    <br>
    <p v-if="maximumReached" style="color: red;">Sorry, you can only have a maximun of 5 tasks everyday.</p>
    <p v-else>Trail members have a limit of 5 tasks that can be created everyday</p>
    <p>Add a new todo:</p>
    <input type="text" v-model="newTask.name" v-on:keyup.enter="submit">
  </div>
</template>


<script>
  export default{
    name: 'todo',
    data () {
      return {
        tasks: [
          {
            name: 'finish homework',
            completed: false
          },
          {
            name: 'Meet highschool friends',
            completed: false
          },
          {
            name: 'play basketball in the gym',
            completed: false
          }
        ],
        newTask: {
          name: '',
          completed: false
        },
        maximumReached: false
      }
    },
    methods: {
      submit: function () {
        if (this.maximumReached === false) {
          if (this.tasks.length >= 5) {
            this.maximumReached = true
            window.alert('no more adding tasks!')
            return false
          }
          this.tasks.push(this.newTask)
          this.newTask = {
            name: '',
            completed: false
          }
        } else {
          window.alert('no more adding tasks!')
        }
      }
    }
  }
</script>

<style scoped>
  .to-do{
    width: 500px;
    margin: 0 auto;
    text-align: left;
  }

  .checked{
    text-decoration: line-through;
  }

  .clear:after{
    content: '';
    display: block;
    clear: both;
  }
</style>
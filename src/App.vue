<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" :showAddTask="showAddTask"/>
    <div v-show="showAddTask">
      <AddTask @add-task="addTask"/>
    </div>
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>

  </div>
</template>

<script>

import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
import AddTask from './components/AddTask.vue'
export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  }, 
  data(){
      return {
        tasks: [],
        showAddTask: true,
      }
    },
    created(){
      this.tasks = [
      {
        id: 1,
        text: 'Buy food',
        day: 'August 1st at 8:00am',
        reminder: true
      },
      {
        id: 2,
        text: 'Doctors appointment',
        day: 'August 3rd at 12:00pm',
        reminder: true
      },
      {
        id: 3,
        text: 'Meeting at school',
        day: 'August 5th at 9:00 am',
        reminder: true
      }
      ]
    },
    methods: {
      deleteTask(id){
        if(confirm('Are you sure?')){
          this.tasks = this.tasks.filter((task) => task.id !== id);
        }
      },
      toggleReminder(id){
        this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} :task)
      },
      addTask(task) {
        this.tasks = [...this.tasks, task];
      }, 
      toggleAddTask(){
        this.showAddTask = !this.showAddTask;
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

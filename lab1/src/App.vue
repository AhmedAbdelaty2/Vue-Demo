<template>
<div class="container">
  <div class="my-2">
    <button class="btn btn-outline-primary mx-2" @click="view = 'form'">From</button>
    <button class="btn btn-outline-primary mx-2" @click="view = 'students'">Students</button>
    <button class="btn btn-outline-primary mx-2" @click="view = 'admins'">Admins</button>
  </div>
  <formApp @newPerson="newRecord" v-if="view==='form'"/>
  <studentsApp v-else-if="view==='students'"/>
  <adminsApp v-else-if="view==='admins'"/>
</div>
</template>

<script>
import formApp from './components/form.vue'
import studentsApp from './components/studentsList.vue'
import adminsApp from './components/adminsList.vue'

export default {
  name: 'App',
  data() {
    return {
      name:"Ahmed",
      students: [],
      admins:[],
      view:'form',
    }
  },
  components: {
    formApp,
    studentsApp,
    adminsApp
  },
  provide() {
    return{
      students: this.students,
      admins: this.admins,
      }
  },
  methods: {
    newRecord(person){
      if(person.type==='admin'){
        this.admins.push(person);
      }else if(person.type==='student'){
        this.students.push(person);
      }
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
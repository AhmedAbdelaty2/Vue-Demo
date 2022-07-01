<template>
  <div class="tabs">
    <button @click="tab = 'form'">Form</button>
    <button @click="tab = 'students'">Students</button>
    <button @click="tab = 'admins'">Admins</button>
  </div>
  <FormComponent @add="addUser" v-if="tab === 'form'" />
  <StudentsTable @delete="deleteUser" :students="students" v-if="tab === 'students'" />
  <AdminsTable @delete="deleteUser" :admins="admins" v-if="tab === 'admins'" />
</template>

<script setup>

import {ref} from "vue";
import FormComponent from "@/components/FormComponent";
import StudentsTable from "@/components/StudentsTable";
import AdminsTable from "@/components/AdminsTable";

const students = ref([]);
const admins = ref([]);
const tab = ref('form');


function addUser(data) {
  if (data.type === 'admin')
    admins.value.push(data.user);
  else
    students.value.push(data.user);

  data.user = {};
}

function deleteUser(data) {
  if (data.type === 'admin')
    admins.value.splice(data.index, 1);
  else
    students.value.splice(data.index, 1);
}

</script>

<style>

body {
  margin: 0;
  background-color: #7c80e4;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  padding: 1rem;
  color: #7c80e4;
  font-weight: bold;
  background-color: black;
  cursor: pointer;
  border-radius: 5px;
}

.tabs {
  display: flex;
  justify-content: center;
  align-items: center;
}

.tabs button {
  margin-inline: 0.5rem;
}

table, th, td {
  margin: auto;
  padding: 1px;
  border: 1px solid black;
}

</style>

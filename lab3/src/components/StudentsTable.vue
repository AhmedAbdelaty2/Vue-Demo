<template>
  <h1>Students</h1>
  <table>
    <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>Address</th>
      <th>Action</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="(student,index) in props.students" :key="index">
      <td>{{ student.name }}</td>
      <td>{{ student.age }}</td>
      <td>{{ student.address }}</td>
      <td>
        <button @click="emit('delete', {type: 'student', index: index})">Delete</button>
      </td>
    </tr>
    </tbody>
  </table>
</template>

<script setup>
import {defineEmits, defineProps} from "vue";

const props = defineProps(['students']);
const emit = defineEmits(['delete']);
</script>

<style scoped>

</style>

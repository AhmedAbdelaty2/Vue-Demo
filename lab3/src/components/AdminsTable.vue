<template>
  <h1>Admins</h1>
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
    <tr v-for="(admin,index) in props.admins" :key="index">
      <td>{{ admin.name }}</td>
      <td>{{ admin.age }}</td>
      <td>{{ admin.address }}</td>
      <td>
        <button @click="emit('delete', {type: 'admin', index: index})">Delete</button>
      </td>
    </tr>
    </tbody>
  </table>
</template>

<script setup>
import {defineEmits, defineProps} from "vue";

const props = defineProps(['admins']);
const emit = defineEmits(['delete']);
</script>

<style scoped>

</style>

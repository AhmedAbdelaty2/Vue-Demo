<template>
  <form @submit.prevent="emit('add', data)">
    <input type="text" placeholder="Enter Name" v-model.trim="data.user.name"/>
    <input type="text" placeholder="Enter Age" v-model.trim.number="data.user.age"/>
    <input type="text" placeholder="Enter Address" v-model.trim="data.user.address"/>
    <div class="radio-group">
      <div class="form-group">
        <input id="student-radio" name="type" type="radio" value="student" v-model="data.type" checked/>
        <label for="student-radio">Student</label>
      </div>
      <div class="form-group">
        <input id="admin-radio" name="type" type="radio" value="admin" v-model="data.type"/>
        <label for="admin-radio">Admin</label>
      </div>
    </div>
    <button type="submit" value="Add User">Add User</button>
  </form>
</template>

<script setup>
import {defineEmits, ref} from "vue";

const data = ref({
  user: {
    name: "",
    age: "",
    address: "",
  },
  type: "students"
});

const emit = defineEmits(['add']);

</script>

<style scoped>

form {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  row-gap: 1.5rem;
}
input[type=text] {
  color: white;
  background-color: black;
  border: none;
  border-radius: 5px;
  padding: 1rem;
  width: 20%;
}

</style>

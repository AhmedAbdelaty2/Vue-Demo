<template>
    <div :class='inputs' class="my-3">
        <div class="input-group mb-3">
            <input v-model='person.name' type="text" class="form-control" placeholder="Name" aria-label="name" aria-describedby="basic-addon1">
        </div>
        <div class="input-group mb-3">
            <input  v-model='person.age' type="text" class="form-control" placeholder="Age" aria-label="age" aria-describedby="basic-addon1">
        </div>
        <div class="input-group mb-3">
            <input  v-model='person.city' type="text" class="form-control" placeholder="City" aria-label="city" aria-describedby="basic-addon1">
        </div>
    </div>
    <div :class="menu" class="my-2">
    <select v-model='person.type' class="form-select" aria-label="Default select example">
      <option value="student">Student</option>
      <option value="admin">Admin</option>
    </select>
    <button @click="sendData" class="btn btn-primary my-3">Add User</button>
    </div>
</template>

<script>
    export default {
        name:'formApp',
        emits:['newPerson'],
        data(){
            return{
                inputs:'form',
                menu:'menu',
                
                person:{
                    name:null,
                    age:null,
                    city:null,
                    type:'student',
                }
            }
        },
        methods:{
            sendData(){
                this.$emit('newPerson', this.person);
            }
            // submit(){
            //     console.log(this.person.name)
            //     console.log(this.person.age)
            //     console.log(this.person.city)
            //     console.log(this.person.type)
            // }
        }
    }

</script>

<style scoped>
.form{
    width:50%;
    position: relative;
    transform: translate(-50%,0);
    left: 50%;
}

.menu{
  width:20%;
  position: relative;
  transform: translate(-50%,0);
  left: 50%;
}
</style>
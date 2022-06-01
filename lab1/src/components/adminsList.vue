<template>
    <div>
        <table class="table table-striped|sm|bordered|hover|inverse table-inverse table-responsive">
            <thead class="thead-inverse|thead-default">
                <tr>
                    <th>Name</th>
                    <th>Age</th>
                    <th>City</th>
                </tr>
                </thead>
                <tbody>
                    <tr v-for="admin in admins" :key="admin.name">
                        <td>{{admin.name}}</td>
                        <td>{{admin.age}}</td>
                        <td>{{admin.city}}</td>
                    </tr>
                </tbody>
        </table>
        
    </div>
</template>

<script>
    export default {
        name:'adminsApp',
        inject:['admins'],
    }
</script>

<style scoped>

</style>
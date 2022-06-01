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
                    <tr v-for="student in students" :key="student.name">
                        <td>{{student.name}}</td>
                        <td>{{student.age}}</td>
                        <td>{{student.city}}</td>
                    </tr>
                </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        name:'studentsApp',
        inject:['students'],
    }
</script>

<style scoped>

</style>
<template>
    <table class="table table-striped table-hover">
        <thead>
            <tr>
                <th>#</th>
                <th>Photo</th>
                <th>Name</th>
                <th>Email</th>
                <th>Sex</th>
                <th>Birtdate</th>
                <th>Actions</th>
            </tr>
        </thead>
        <tbody id="tableEmployees" v-for="employee in this.employees" :key="employee.id">
            <tr>
                <td>{{employee.id}}</td>
                <td>{{employee.profilePicture}}</td>
                <td>{{employee.name}}</td>
                <td>{{employee.email}}</td>
                <td>{{employee.gender}}</td>
                <td>{{employee.birthdate}}</td>
                <td><div class="delete-container"><a href="#" class="delete" title="Delete" data-toggle="tooltip"><i class="material-icons">&#xE5C9;</i></a></div></td>
            </tr>
            
        </tbody>
    </table>
</template>

<script>
import axios from "axios";
import Modal from "./Modal.vue"

export default {
    data() {
        return {
            employees: []
        }
    },
    mounted() {
        console.log('Component mounted.')
        console.log(this.getEmployees());
    },
        methods: {
            async getEmployees() {
                    
                // return [{"id":2,"profilePicture":"valid picture","name":"Adrian Negreanu-Maior","email":"adrian.negreanu@principal33.com","gender":"Male","birthdate":"6 February 1972"},{"id":10002,"profilePicture":null,"name":"Adrian Negreanu-Maior","email":null,"gender":null,"birthdate":null},{"id":20002,"profilePicture":"valid picture","name":"Adrian Negreanu-Maior","email":"adrian.negreanu@principal33.com","gender":"Male","birthdate":"6 February 1972"},{"id":30002,"profilePicture":"valid picture","name":"Adrian Negreanu-Maior","email":"adrian.negreanu@principal33.com","gender":"Male","birthdate":"6 February 1972"},{"id":1,"profilePicture":"valid picture","name":"Gabriel Negreanu","email":"gabriel.negreanu@principal33.com","gender":"Male","birthdate":"31 December 2001"}]
                // let currentObj = this;
                axios.get('https://localhost:44302/api/Employee', 
                    {
                        headers: {
                            "Access-Control-Allow-Origin": "*"
                        }
                    })
                .then(function (response) {
                    this.employees = response.data;
                })
                .catch(function (error) {
                    console.log(error);
                });
            }
        }
}
</script>

<style scoped>
table.table tr th, table.table tr td {
    border-color: #e9e9e9;
    padding: 12px 15px;
    vertical-align: middle;
}

table.table tr th:first-child {
    width: 60px;
}

table.table tr th:last-child {
    width: 100px;
}

table.table-striped tbody tr:nth-of-type(odd) {
    background-color: #fcfcfc;
}

table.table-striped.table-hover tbody tr:hover {
    background: #f5f5f5;
}

table.table th i {
    font-size: 13px;
    margin: 0 5px;
    cursor: pointer;
}

table.table td:last-child i {
    opacity: 0.9;
    font-size: 22px;
    margin: 0 5px;
}

table.table td a {
    font-weight: bold;
    color: #566787;
    display: inline-block;
    text-decoration: none;
}

table.table td a:hover {
    color: #2196F3;
}

table.table td a.delete {
    color: #F44336;
    border-radius: 50%;
    padding-top: 5px;
}

.delete-container {
    width: fit-content;
    justify-content: center;
    align-items: center;
    margin-left: 15px;
}

.delete-container:hover {
    box-shadow: 2px 2px 3px 3px #1b1c30;
    border-radius: 50%;
}

table.table td i {
    font-size: 19px;
}

.picture {
    border-radius: 50%;
    vertical-align: middle;
    margin-right: 10px;
    width: 40px;
}
</style>
<template>
    <Modal @new-employee-added="getEmployees"></Modal>
    <div class="table-options">
        <div class="search-bar">
            <div class="input-group">
                <div class="form-outline">
                    <input type="search" id="search-employee" class="form-control" placeholder="Find employees..." v-model="search" />
                    <button class="button" @click="searchEmployees">Search</button>
                </div>
            </div>
        </div>
        <p class="sort-description">Filter by gender:</p>
        <select class="form-select sort-select" id="table-sort-by" v-model="gender">
            <option class="sort-option" selected value="Male">Male</option>
            <option class="sort-option" value="Female">Female</option>
        </select>
        <button id="filterButton" class="button" @click="filterEmployees">Filter</button>
    </div>
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
        <tbody id="tableEmployees">
            <tr v-for="(employee, index) in employees" :key="employee.id">
                <td>{{index + 1}}</td>
                <td>{{employee.profilePicture}}</td>
                <td>{{employee.name}}</td>
                <td>{{employee.email}}</td>
                <td>{{employee.gender}}</td>
                <td>{{employee.birthdate}}</td>
                <td><div class="delete-container"><a href="#" class="delete" title="Delete" data-toggle="tooltip" @click="deleteClick(employee.id)"><i class="material-icons">&#xE5C9;</i></a></div></td>
            </tr>
            
        </tbody>
    </table>
</template>

<script>
import axios from "axios";
import Modal from "./Modal.vue";

export default {
    
    components: {
        Modal,
    },

    data() {
        return {
            employees: []
        }
    },
    mounted() {
        console.log('Component mounted.')
        this.getEmployees()
    },
        methods: {
            getEmployees() {
                    
                axios.get('https://localhost:44302/api/Employee', 
                    {
                        headers: {
                            "Access-Control-Allow-Origin": "*"
                        }
                    })
            
                .then((response) => {
                this.employees = response.data;
                })
                .catch((error) => {
                this.errorMessage = error.message;
                console.error("There was an error!", error);
                });
            },
            deleteClick(id) {
                if (!confirm("Are you sure?")) {
                    return;
                }
                axios.delete('https://localhost:44302/api/Employee/' + id).then(() => {
                    this.employees = this.getEmployees();
                });
            },

            searchEmployees() {
                axios.get('https://localhost:44302/api/Employee/search/' + this.search).then((response) => {
                    this.employees = response.data;
                    console.log(response.data);
                })
                
            },

            filterEmployees() {
                axios.get('https://localhost:44302/api/Employee/filter/' + this.gender).then((response) => {
                    this.employees = response.data;
                    console.log(response.data);
                })
                
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

.button {
    background-color: #6235ff;
    color: #fff;
    width: fit-content;
    padding: 5px 20px;
    margin-top: 15px;
    border: none;
    border-radius: 2px;
}

.button:hover {
    background-color: #ff8348;
}
</style>
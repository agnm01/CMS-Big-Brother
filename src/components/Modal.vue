<template>
 <div class="container p-5">
    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">Add an employee</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="errors" v-if="errors.length">
                    <h3>Please correct the following error(s):</h3>
                    <ul>
                    <li v-for="error in errors" :key="error">{{ error }}</li>
                    </ul>
                </div>
                <div class="modal-body">
                    <div class="mb-3">
                        <label for="last-name" class="form-label"><span class="required-field">*</span> Name</label>
                        <input type="text" class="form-control" id="name-input" placeholder="Employee name" v-model="name" required>
                    </div>
                    <div class="mb-3">
                        <label for="email-input" class="form-label"><span class="required-field">*</span> Email</label>
                        <input type="email" class="form-control" id="email-input" placeholder="name@example.com" v-model="email" required>
                    </div>

                    <div class="mb-3">
                        <label for="sex-input" class="form-label"><span class="required-field">*</span> Gender</label>
                        <select class="form-select" id="sex-input" v-model="gender" required>
                            <option value="" selected disabled>Select gender</option>
                            <option value="Male">Male</option>
                            <option value="Female">Female</option>
                        </select>
                    </div>

                    <div class="mb-3">
                        <label for="birthdate-input" class="form-label"><span class="required-field">*</span> Date of birth</label>
                        <input type="date" class="form-control" id="birthdate-input" max="today" placeholder="" v-model="birthdate" required>
                    </div>

                    <div class="modal-footer">
                        <button class="modal-cancel-btn" data-bs-dismiss="modal" ref="closeBtn" aria-label="Close">Close</button>
                        <button type="submit" class="modal-add-btn" id="addEmployeeModal" @click="submitEmployee">Submit</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>
<script>
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap/dist/js/bootstrap.min.js";
import axios from "axios";

export default {
        mounted() {

            console.log('Component mounted.')
        },
        data() {
            
            return {
                errors: [],
                name: '',
                email: '',
                gender: '',
                birthdate: '',
                profilePicture: ''
            };
        },
        methods: {

            addClick() {
                this.EmployeeId = 0;
                this.profilePicture = "profile_pic.png";
                this.name = "";
                this.email = "";
                this.gender = "";
                this.birthdate = "";
            },

            submitEmployee(e) {
                e.preventDefault();
                this.checkForm();
                if(this.errors.length) {
                    return;
                }
                axios.post('https://localhost:44302/api/Employee', {
                    name: this.name,
                    email: this.email,
                    gender: this.gender,
                    birthdate: this.birthdate,
                    profilePicture: this.profilePicture,
                })
                this.$refs.closeBtn.click();
            },

            checkForm: function () {
                this.errors = [];

                if (!this.name) {
                    this.errors.push("Name required.");
                }
                if (!this.email) {
                    this.errors.push('Email required.');
                } else if (!this.validEmail(this.email)) {
                    this.errors.push('Valid email required.');
                }
                if (!this.gender) {
                    this.errors.push("Gender required.");
                }
                if (!this.birthdate) {
                    this.errors.push("Birthdate required.");
                }

                if (!this.errors.length) {
                    return true;
                }
            },

            validEmail: function (email) {
                var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                return re.test(email);
            }

            
        }
    }
</script>

<style scoped>

.errors {
    background-color: crimson;
    color: white;
    margin: 10px auto;
    padding: 10px;
    border-radius: 2px;
}

.errors h3 {
    font-size: 18px;
}
.required-field {
    color: #ff5b5b;
}
.modal-cancel-btn {
    background-color: #6235ff;
    color: #fff;
    width: fit-content;
    padding: 5px 20px;
    margin-top: 15px;
    border: none;
    border-radius: 2px;
}

.modal-add-btn {
    background-color: #ff8348;
    color: #fff;
    width: fit-content;
    padding: 5px 20px;
    margin-top: 15px;
    border: none;
    border-radius: 2px;
}
</style>
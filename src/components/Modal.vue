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

                    <div class="mb-3">
                        <label for="picture" class="form-label">Add avatar</label>
                        <input class="form-control" type="text" id="picture-input" v-model="profilePicture">
                        <br>
                        <img id="imgPreview" class="preview-profile-pic" src="" height=150>
                    </div>

                    <div class="modal-footer">
                        <button class="modal-cancel-btn" data-bs-dismiss="modal" aria-label="Close">Cancel</button>
                        <button type="submit" class="modal-add-btn" id="addEmployeeModal" data-bs-dismiss="modal" @click="submitEmployee">Submit</button>
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
                axios.post('https://localhost:44302/api/Employee', {
                    name: this.name,
                    email: this.email,
                    gender: this.gender,
                    birthdate: this.birthdate,
                    profilePicture: this.profilePicture,
                })
            }

            
        }
    }
</script>

<style scoped>
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
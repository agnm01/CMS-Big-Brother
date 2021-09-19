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
                        <input type="text" class="form-control" id="name-input" placeholder="Employee name" v-model="formData.name" required>
                    </div>
                    <div class="mb-3">
                        <label for="email-input" class="form-label"><span class="required-field">*</span> Email</label>
                        <input type="email" class="form-control" id="email-input" placeholder="name@example.com" v-model="formData.email" required>
                    </div>

                    <div class="mb-3">
                        <label for="sex-input" class="form-label"><span class="required-field">*</span> Gender</label>
                        <select class="form-select" id="sex-input" v-model="formData.gender" required>
                            <option value="" selected disabled>Select gender</option>
                            <option value="Masculin">Male</option>
                            <option value="Feminin">Female</option>
                        </select>
                    </div>

                    <div class="mb-3">
                        <label for="birthdate-input" class="form-label"><span class="required-field">*</span> Date of birth</label>
                        <input type="date" class="form-control" id="birthdate-input" max="today" placeholder="" v-model="formData.birthdate" required>
                    </div>

                    <div class="mb-3">
                        <label for="picture" class="form-label">Add avatar</label>
                        <input class="form-control" type="file" id="picture-input" accept="image/*">
                        <br>
                        <img id="imgPreview" class="preview-profile-pic" src="" height=150>
                    </div>
                    
                    <div class="modal-footer">
                        <button class="modal-cancel-btn" data-bs-dismiss="modal" aria-label="Close">Cancel</button>
                        <button type="submit" class="modal-add-btn" id="addEmployeeModal" @click="submitEmployee" data-bs-dismiss="modal">Submit</button>
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

export default {
    data() {
        return {
            formData: {
                name: "",
                email: "",
                gender: "",
                birthdate: ""
            }
        };
    },
    methods: {
        submitEmployee() {
            console.log(this.formData);
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
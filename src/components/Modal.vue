<template>
    <div class="modal fade" id="myModal">
        <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content">
                <div class="modal-header modal-header-gradient">
                    <h5 class="modal-title" id="exampleModalLongTitle">Add an employee</h5>
                    <button type="button" class="btn-close close-myModal"></button>
                </div>

                <div class="modal-body">

                    <form>
                        <div class="mb-3">
                            <label for="last-name" class="form-label"><span class="required-field">*</span> Name</label>
                            <input type="text" class="form-control" id="name-input" placeholder="Employee name" required>
                        </div>

                        <div class="mb-3">
                            <label for="email-input" class="form-label"><span class="required-field">*</span> Email</label>
                            <input type="email" class="form-control" id="email-input" placeholder="name@example.com" required>
                        </div>

                        <div class="mb-3">
                            <label for="sex-input" class="form-label"><span class="required-field">*</span> Sex</label>
                            <select class="form-select" id="sex-input" required>
                                <option value="" selected disabled>Select sex</option>
                                <option value="Masculin">Male</option>
                                <option value="Feminin">Female</option>
                            </select>
                        </div>

                        <div class="mb-3">
                            <label for="birthdate-input" class="form-label"><span class="required-field">*</span> Date of birth</label>
                            <input type="date" class="form-control" id="birthdate-input" max="today" placeholder="" required>
                        </div>

                        <div class="mb-3">
                            <label for="picture" class="form-label">Add avatar</label>
                            <input class="form-control" type="file" id="picture-input" accept="image/*">
                            <br>
                            <img id="imgPreview" class="preview-profile-pic" src="" height=150>

                        </div>
                        <div class="modal-footer">
                            <button type="submit" class="modal-cancel-btn close-myModal">Cancel</button>
                            <button type="submit" class="modal-add-btn" id="addEmployeeModal">Submit</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script></script>

<style scoped></style>
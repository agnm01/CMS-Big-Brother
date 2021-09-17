<template>
    <div class="table-title">
        <h2>Employee Management</h2>
        <a href="#" class="btn btn-primary" id="openEmployeeModal">
            <i class="material-icons">&#xE147;</i>
            <span>Add New Employee</span>
        </a>
    </div>
</template>

<script>
</script>

<style scoped>
.table-title {
    padding-bottom: 15px;
    color: #fff;
    padding: 16px 30px;
    margin: -20px -25px 10px;
    border-radius: 3px 3px 0 0;
    display: flex;
    justify-content: space-between;
    background: linear-gradient(90deg, #ff8348, #6235ff);
    background-size: 100% 100%;
    scroll-behavior: none;
}

.table-title h2 {
    margin: 5px 0 0;
    font-size: 24px;
}

.table-title .btn {
    color: #566787;
    float: right;
    font-size: 13px;
    background: #fff;
    border: none;
    min-width: 50px;
    border-radius: 2px;
    border: none;
    outline: none !important;
    margin-left: 10px;
}

.table-title .btn:hover,
.table-title .btn:focus {
    color: #566787;
    background: #f2f2f2;
}

.table-title .btn i {
    float: left;
    font-size: 21px;
    margin-right: 5px;
}

.table-title .btn span {
    float: left;
    margin-top: 2px;
}
</style>
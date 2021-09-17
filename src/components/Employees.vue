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
        <tbody id="tableEmployees"></tbody>
    </table>
</template>

<script></script>

<style scoped>
table.table tr th,
table.table tr td {
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
<template>
    <p class="sort-description">Filter by:</p>
    <select class="form-select sort-select" id="table-sort-by">
        <option class="sort-option" selected value="name">Gender</option>
        <option class="sort-option" value="birthdate">Profile picture</option>
    </select>
    <button id="filterButton" class="filter-button">Filter</button>
</template>

<script></script>

<style scoped>
.sort-description {
    margin-top: 15px;
}
.filter-button {
    background-color: #6235ff;
    color: #fff;
    width: fit-content;
    padding: 5px 20px;
    margin-top: 15px;
    border: none;
    border-radius: 2px;
}

.filter-button:hover {
    background-color: #ff8348;
}
</style>
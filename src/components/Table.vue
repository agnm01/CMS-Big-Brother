<template>
    <div class="table-responsive">
        <div class="table-wrapper">
            <TableHeader></TableHeader>
            <div class="table-options">
                <Search></Search>

                <p class="sort-description">Filter by:</p>
                <select class="form-select sort-select" id="table-sort-by">
                    <option class="sort-option" selected value="name">Name</option>
                    <option class="sort-option" value="birthdate">Date of birth</option>
                </select>
                <p class="sort-description">Sort as:</p>
                <select class="form-select sort-select" id="table-sort-order">
                    <option class="sort-option" selected value="ascendent">Ascending</option>
                    <option class="sort-option" value="descendent">Descending</option>
                </select>

                <button id="filterButton" class="filter-button">Filter</button>
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
                <tbody id="tableEmployees"></tbody>
            </table>
        </div>
    </div>
</template>

<script>
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

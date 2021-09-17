<template>
    <div class="table-responsive">
        <div class="table-wrapper">
            <TableHeader></TableHeader>
            <div class="table-options">
                <Search></Search>
                <FilterBy></FilterBy>
            </div>
            <Employees></Employees>
        </div>
    </div>
</template>

<script>
import TableHeader from './TableHeader.vue'
import Search from './Search.vue'
import FilterBy from './FilterBy.vue'
import Employees from './Employees.vue'
export default {
    components: {
        TableHeader: TableHeader,
        Search: Search,
        FilterBy: FilterBy,
        Employees: Employees
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.table-responsive {
    margin: 30px 0;
}

.table-wrapper {
    min-width: 1000px;
    background: #fff;
    padding: 20px 25px;
    border-radius: 3px;
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
</style>

<template>
    <div class="table-responsive">
        <div class="table-wrapper">
            <TableHeader></TableHeader>
            <div class="table-options">
                <Search></Search>
                <FilterBy></FilterBy>
            </div>
            
        </div>
    </div>
</template>

<script>
import TableHeader from './TableHeader.vue'
import Search from './Search.vue'
import FilterBy from './FilterBy.vue'
export default {
    components: {
        TableHeader: TableHeader,
        Search: Search,
        FilterBy: FilterBy
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

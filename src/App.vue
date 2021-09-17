<template>
  <Modal></Modal>
  <Table>
    <TableHeader></TableHeader>
    <Search></Search>
    <FilterBy></FilterBy>
    <Employees></Employees>
  </Table>
</template>

<script>
import Table from './components/Table.vue'
import TableHeader from './components/TableHeader.vue'
import Search from './components/Search.vue'
import FilterBy from './components/FilterBy.vue'
import Employees from './components/Employees.vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Table,
    TableHeader,
    Search,
    FilterBy,
    Employees,
    Modal
  }
}
</script>

<style>
html, #app {
  background-color: #1b1c30;
}

body {
  color: #566787;
  background: #f5f5f5;
  font-family: "Varela Round", sans-serif;
  font-size: 13px;
}
</style>

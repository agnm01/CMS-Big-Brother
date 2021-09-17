<template>
  <Table>
    <TableHeader></TableHeader>
    <Search></Search>
  </Table>
</template>

<script>
import Table from './components/Table.vue'
import TableHeader from './components/TableHeader.vue'
import Search from './components/Search.vue'

export default {
  name: 'App',
  components: {
    Table,
    TableHeader,
    Search
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

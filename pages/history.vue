<template>
  <div class="wrapper">
    <h3>history page</h3>
    <app-crud></app-crud>
    <restock-table></restock-table>
  </div>

</template>

<script>
import AppCrud from '~/components/appCrud.vue'
import AppTable from '~/components/AppTable.vue'
import feedTable from '~/components/feedTable.vue'
import RestockTable from '~/components/restockTable.vue'
export default {
  components: { feedTable, AppCrud, AppTable, RestockTable },

}
</script>

<style>

</style>
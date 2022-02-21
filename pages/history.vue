<template>
  <div class="wrapper">
    <h3>history page</h3>
    <app-crud></app-crud>
  </div>

</template>

<script>
import AppCrud from '~/components/appCrud.vue'
import feedTable from '~/components/feedTable.vue'
export default {
  components: { feedTable, AppCrud },

}
</script>

<style>

</style>
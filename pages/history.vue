<template>
  <div class="wrapper">
    <h3>history page</h3>
    <app-crud></app-crud>
    <restock-table></restock-table>
    <notice message="Item created successfully"/>
  </div>

</template>

<script>
import Notice from '~/components/modals/Notice.vue'
 
export default {
  components: { Notice },

}
</script>

<style>

</style>
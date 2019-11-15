<template>
  <div class="col-md-8">
    <cm></cm>
    <buy-sell-card></buy-sell-card>
    <data-entry-form></data-entry-form>
  </div>
</template>

<script>
import CM from './cm.vue'
import BuySellCard from './buy_sell_card.vue'
import DataEntryForm from './data_entry_form.vue'
export default {
  components: {
    cm: CM,
    'buy-sell-card': BuySellCard,
    'data-entry-form': DataEntryForm
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>

<template>
  <div class="flex rounded-lg mt-2 pr-2 shadow-md overflow-hidden" style="background:#E4E2E2;">
    <div class="p-2 random-color" style="background:#687781;">
      <div
        class="text-purple-400 uppercase tracking-wider text-sm"
        style="color: white;"
      >Trans No. {{this.transaction.t_no}}</div>
      <div
        class="text-white text-1xl"
        style="font-weight: bolder;"
      >Currency pair {{this.transaction.curr_pair}}</div>
      <div
        class="text-purple-400 text-sm"
        style="color: white; margin-top: 10px;"
      >Comment: processed</div>
    </div>
    <div class="p-2" style="background:#E4E2E2;">
      <div class="flex justify-between">
        <div
          class="text-purple-400 uppercase tracking-wider text-sm"
          style="color: #646464;"
        >Customer ID: {{this.transaction.cust_id}}</div>
        <div class="pt-1 pl-8">
          <div
            class="text-xs text-purple-400 text-right uppercase"
            style="color: #646464;"
          >Rate: {{this.transaction.rate}}</div>
        </div>
      </div>
      <div
        class="text-1xl text-purple-900"
        style="color: #646464; font-weight: bolder;"
      >FC Amount : {{this.transaction.fc_amt}}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    transaction: {}
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.text-sm {
  font-size: 0.65rem;
}
</style>

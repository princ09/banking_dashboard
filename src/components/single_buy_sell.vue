<template>
  <div class="rounded-lg bg-white mt-2 mr-2 shadow-md overflow-hidden" @click="passToDataEntry">
    <div
      class="text-1xl text-purple-900 items-center text-center"
      style="background:rgb(93, 137, 168); color: white;"
    >{{curr_pair_buy}}/{{curr_pair_sell}}</div>
    <div class="flex antialiased justify-center items-center" id="style-2" style="float: left;">
      <div class="p-2" style="background:#687781;">
        <div class="text-purple-400 uppercase tracking-wider text-2xl" style="color: white;">BUY</div>
      </div>
      <div class="p-2" style=" background: #E4E2E2; color:#646464;">
        <div class="text-2xl text-purple-900" style="color:#687781; font-weight: bolder;">SELL</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    curr_pair_buy: {
      type: String
    },
    curr_pair_sell: {
      type: String
    }
  },
  methods: {
    passToDataEntry() {
      this.$root.$emit(
        "pass_to_dataEntry",
        this.curr_pair_buy,
        this.curr_pair_sell
      );
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>

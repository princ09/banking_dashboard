<template>
  <div class="row">
    <div class="justify-center ml-3 pb-2 items-center" id="style-2"
      style=" display: flex; overflow-y: scroll; height: 92px; flex-wrap: wrap; ">
      <single-buy-sell v-for="(curr_pair,index) in this.curr_pair_list" :key="index" :curr_pair_buy="curr_pair.buy" :curr_pair_sell="curr_pair.sell"></single-buy-sell>
    </div>
  </div>
</template>

<script>
import SingleBuySell from './single_buy_sell'
export default {
    data(){
        return{
            curr_pair_list:[]
        }
    },
  components: {
    'single-buy-sell': SingleBuySell
  },
  
   mounted() {
     this.$root.$on('pass_cust_id' , (id) => {
       axios.get("http://localhost:3000/customer/"+id).then(response => {
        console.log(response.data)
        this.curr_pair_list = response.data.curr_pair_list;
    })
     })
 
 }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>

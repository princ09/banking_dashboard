<template>
  <div class="row">
    <div class="search-box mt-2">
      <form method="post">
        <input
          type="text"
          class="textbox"
          v-model="search"
          style="background:#e4e2e2;"
          placeholder="Search Transactions"
        />
        <input title="Search" value="" type="submit" class="button trans" />
      </form>
    </div>
    <div
      class="antialiased justify-center pr-2 items-center"
      id="style-2"
      style="overflow-y: scroll;height: 420px; min-height: 420px; "
    >
      <trans-card
        v-for="transaction in this.filteredList"
        v-bind:key="transaction.c_id"
        v-bind:transaction="transaction"
      ></trans-card>
    </div>
  </div>
</template>

<script>
import TransCard from "./transaction_card.vue";

export default {
  props: {},
  data() {
    return {
      search: "",
      id: 0,
      transactions: []
    };
  },
  components: {
    "trans-card": TransCard
  } /*
  watch:{
    cust_id:function(){
      console.log(cust_id)
       axios.get("http://localhost:3000/customer/"+this.cust_id).then(response => {
        console.log(response.data)
        this.transactions = response.data.transactions;
    })
    }
  },*/,
  computed: {
    filteredList() {
      return this.transactions.filter(transaction => {
        return transaction.t_no.toString().includes(this.search.toString());
      });
    }
  },
  methods: {
    getData() {}
  },
  mounted() {
    this.$root.$on("pass_cust_id", id => {
      axios.get("http://localhost:3000/customer/" + id).then(response => {
        this.transactions = response.data.transactions;
      });
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
input:focus {
}
form > .textbox:focus {
  background: rgb(93, 137, 168);
  color: white;
}
</style>

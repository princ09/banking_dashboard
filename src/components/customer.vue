<template>
  <div>
    <div class="row">
      <div class="search-box">
        <form>
          <input
            style="background:#E4E2E2; color:#646464;"
            type="text"
            class="textbox"
            placeholder="Search Customer"
            v-model="cust_query"
            value="0"
          />
          <input
            title="Search"
            value=""
            type="submit"
            class="button"
            @click.prevent="queryResults"
          />
        </form>
      </div>
    </div>
    <div class="row">
      <div class="antialiased justify-center items-center">
        <div class="flex rounded-lg bg-white mt-2 shadow-md overflow-hidden">
          <div class="p-2" style="background: rgb(93, 137, 168)">
            <div class="text-purple-400 uppercase tracking-wider text-sm" style="color: white;">
              <b>Customer Id:</b>
              {{custList.id}}
            </div>
            <div class="text-white text-1xl">
              <b>Name:</b>
              {{custList.name}}
            </div>
          </div>
          <div class="p-2" style="background:#E4E2E2; color:#646464;">
            <div class="flex justify-between">
              <div class="uppercase tracking-wider text-sm">
                <b>Transaction Branch:</b>
                {{custList.t_branch}}
              </div>
            </div>
            <div class="text-1xl">
              <b>margin:</b>
              {{custList.margin}}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import fz from "fuzzaldrin-plus";
const axios = require("axios");
export default {
  data() {
    return {
      cust_query: "0",
      custList: [],
      results: []
    };
  },
  methods: {
    queryResults() {
      /*if (!this.cust_query) return this.custList
      console.log(this.custList)
      console.log(cust_query)

      const preparedQuery = fz.prepareQuery(this.cust_query)
      const scores = {}

      this.results = this.custList.map((cust, index) => {
        const scorableFields = [cust.id, cust.name].map(toScore =>
         fz.score(toScore, this.cust_query, { preparedQuery })
        )
      scores[cust.id] = Math.max(...scorableFields)
      return cust;
        })
        .filter(cust => scores[cust.id] > 1)
        .sort((a, b) => scores[b.id] - scores[a.id])*/
      axios
        .get("http://localhost:3000/customer/" + this.cust_query)
        .then(response => {
          this.custList = response.data;
          this.$root.$emit("pass_cust_id", this.custList.id);
          this.$emit("gotCustId", this.custList.id);
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>

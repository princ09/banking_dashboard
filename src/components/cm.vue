<template>
  <div class="row">
    <div class="col-md-4">
      <div class="search-box">
        <form method="post">
          <input
            type="text"
            class="textbox"
            style="width: 84%;color:#646464;background:#E4E2E2;"
            placeholder="Search RM"
            v-model="cm_query"
          />
          <input
            title="Search"
            value=""
            style=" width:16%;"
            type="submit"
            class="button cm"
            @click.prevent="queryResults"
          />
        </form>
      </div>
    </div>
    <div class="col-md-8">
      <div
        class="flex antialiased justify-center items-center vertical-center"
        id="style-3"
        style="float: left;"
      >
        <div class="text-1xl ml-2" style="color:#333333; font-weight:400;">ID:{{this.cmList.id}} |</div>
        <div
          class="text-1xl ml-2"
          style="color:#333333; font-weight:400;"
        >Name: {{this.cmList.name}} |</div>
        <div class="text-1xl ml-2" style="color:#333333; font-weight:400;">{{this.cmList.num}}</div>
        <div class="text-1xl ml-40" style="float: right;">
          <i class="fa fa-cogs text-2xl" aria-hidden="true"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const axios = require("axios");
export default {
  data() {
    return {
      cm_query: "0",
      cmList: []
    };
  },
  methods: {
    queryResults() {
      axios.get("http://localhost:3000/rm/" + this.cm_query).then(response => {
        console.log(response.data);
        this.cmList = response.data;
      });
    }
  }
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>

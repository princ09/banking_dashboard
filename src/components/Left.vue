<template>
  <div class="col-md-4">
    <customer v-on:gotCustId="passToTrans"></customer>

    <transaction v-bind:cust_id="this.id"></transaction>
  </div>
</template>

<script>
import Transaction from "./transactions";
import Customer from "./customer.vue";
export default {
  data() {
    return {
      id: 0
    };
  },
  methods: {
    passToTrans(id) {
      this.id = id;
      console.log(this.id);
    }
  },
  components: {
    transaction: Transaction,
    customer: Customer
  }
};
</script>

<style>
.search-box {
  padding-left: 0;
  margin: 0;
  padding-bottom: 5px;
  width: 100%;
}
form {
  outline: 0;

  -webkit-border-radius: 4px;
  border-radius: 4px;
  padding: 0;
}

form > .textbox {
  outline: 0;
  height: 42px;
  width: 90%;
  line-height: 42px;
  padding: 0 16px;
  background-color: #e4e2e2;
  color: white;
  border: 0;
  float: left;
  -webkit-border-radius: 4px 0 0 4px;
  border-radius: 4px 0 0 4px;
}

form > .textbox:focus {
  outline: 0;
  background-color: #fff;
}

form > .button {
  outline: 0;
  background: none;
  background-color: #687781;
  float: left;
  height: 42px;
  width: 10%;
  text-align: center;
  line-height: 42px;
  border: 0;
  color: #fff;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: 16px;
  text-rendering: auto;
  text-shadow: 0 1px 1px rgba(0, 0, 0, 0.2);
  -webkit-transition: background-color 0.4s ease;
  transition: background-color 0.4s ease;
  -webkit-border-radius: 0 4px 4px 0;
  border-radius: 0 4px 4px 0;
}

form > .button:hover {
  background-color: rgb(93, 137, 168);
}
.trans {
  background: rgb(93, 137, 168);
}
form > .trans:hover {
  background-color: rgb(93, 137, 168);
}
.cm {
  background: rgb(93, 137, 168);
}
form > .cm:hover {
  background-color: rgb(93, 137, 168);
}
.flex-container {
  display: flex;
  flex-wrap: wrap;
  padding: 5px;

  color: #646464;
  background-color: #063bed;
}

.cust_details {
  box-shadow: 2px 5px rgba(0, 0, 0, 0.12);
}

#style-2::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  background-color: #f5f5f5;
}

#style-2::-webkit-scrollbar {
  width: 12px;
  background-color: #f5f5f5;
}

#style-2::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  background-color: #687781;
}
#style-3::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 4px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  background-color: #f5f5f5;
}

#style-3::-webkit-scrollbar {
  width: 12px;
  background-color: #f5f5f5;
}

#style-3::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  background-color: #687781;
}

.vertical-center {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
</style>

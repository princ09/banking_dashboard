<template>
  <div
    class="row ml-1 shadow-md"
    style="background:rgb(93, 137, 168); color:white; border-radius:3px;"
  >
    <div
      class="rounded-lg mt-2 mr-2 p-3 overflow-hidden"
      style=" background:rgb(93, 137, 168);width: 100%;"
    >
      <div class="text-2xl items-center text-center" style="background:rgb(93, 137, 168); ">
        BUY
        <span style="font-weight:400; color:black;">{{this.buy}}</span> SELL
        <span style="font-weight:400; color:black;">{{this.sell}}</span> AT
        <span style="font-weight:400; color:black;">{{this.selectedtenor}}</span>
      </div>

      <form style="background:rgb(93, 137, 168); border:none;">
        <div class="row">
          <div class="col-md-6">
            <li class="form-row">
              <label>Cust Id</label>
              <input type="text" value="189752" />
            </li>
          </div>
          <div class="col-md-6">
            <li class="form-row">
              <label>Crypt Name</label>
              <input type="text" value="Godrej Industries" />
            </li>
          </div>
        </div>
        <div class="row ml-4">
          <input type="radio" selected class="mt-2 pt-2" value="outright" />
          <label class="pl-2">Outright</label>
          <input type="radio" class="ml-2 mt-2 pt-2" value="timeoption" />
          <label class="pl-2">Time Option</label>
        </div>
        <div class="row">
          <div class="col-md-8" style="border-right:2px solid #687781 ;">
            <div class="row">
              <div class="col-md-6">
                <ul class="wrapper">
                  <li class="form-row">
                    <label>Tenor</label>
                    <select v-model="selectedtenor">
                      <option v-for="(val,index) in this.tenor" :key="index">{{val}}</option>
                    </select>
                  </li>
                  <li class="form-row">
                    <label>Buy USD</label>
                    <input type="text" value="1096" />
                  </li>
                  <li class="form-row">
                    <label>Sell INR</label>
                    <input type="text" value="75200.56" />
                  </li>
                  <li class="form-row">
                    <label>Category</label>
                    <select>
                      <option value="default">Default</option>
                      <option value="saab">Saab</option>
                      <option value="opel">Opel</option>
                      <option value="audi">Audi</option>
                    </select>
                  </li>
                  <li class="form-row">
                    <label>EEFC Conv</label>
                    <select>
                      <option value="no">No</option>
                      <option value="saab">Saab</option>
                      <option value="opel">Opel</option>
                      <option value="audi">Audi</option>
                    </select>
                  </li>
                  <li class="form-row">
                    <label>Card Rate</label>
                    <input type="text" value="72.50" disabled />
                  </li>
                </ul>
              </div>
              <div class="col-md-6">
                <ul class="wrapper">
                  <li class="form-row">
                    <label>Maturity date</label>
                    <input type="date" />
                  </li>
                  <li class="form-row">
                    <label>Spot Rate</label>
                    <input type="text" value="71.65" />
                  </li>
                  <li class="form-row">
                    <label>Fwd Pts</label>
                    <input type="text" value="0" />
                  </li>
                  <li class="form-row">
                    <label>Crpt Mrg(BPS)</label>
                    <input type="text" value="25" />
                  </li>
                  <li class="form-row">
                    <label>Bank Mrgs(BPS)</label>
                    <input type="text" value="3" />
                  </li>
                  <li class="form-row">
                    <label>Rate</label>
                    <input type="text" value="71.8900" />
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <div class="col-md-4">
            <ul class="wrapper">
              <li class="form-row">
                <label>Trans type</label>
                <select>
                  <option v-for="(val,index) in this.trans_type" :key="index">{{val}}</option>
                </select>
              </li>
              <li class="form-row">
                <label>Deal type</label>
                <select style="width:60px;">
                  <option v-for="(val,index) in this.deal_type" :key="index">{{val}}</option>
                </select>
              </li>
              <li class="form-row">
                <label>Pay Corr</label>
                <select>
                  <option v-for="(val,index) in this.pre_corr" :key="index">{{val}}</option>
                </select>
              </li>
              <li class="form-row">
                <label>Receive Corr</label>
                <select>
                  <option v-for="(val,index) in this.rec_corr" :key="index">{{val}}</option>
                </select>
              </li>
              <li class="form-row">
                <label>comments</label>
                <textarea type="text"></textarea>
              </li>
            </ul>
          </div>
        </div>
        <div class="row">
          <div class>
            <button class="form-button p-2 ml-32">Accept</button>
            <button class="form-button p-2">Reject</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedtenor: "",
      buy: "",
      sell: "",
      tenor: [
        "CASH",
        "TOM",
        "SPOT",
        "1M",
        "2M",
        "3M",
        "4M",
        "5M",
        "6M",
        "7M",
        "7M",
        "8M",
        "9M",
        "10M",
        "11M",
        "12M",
        "BROKEN"
      ],
      pre_corr: [
        "EURIION_ABNAMRO",
        "SETT-FX",
        "ICICI-HKG",
        "DRES-FFM",
        "INTFESA-SAN",
        "BAYLN-GR",
        "AMEX-FFM",
        "IBOG-LHS",
        "GTSU-CHS",
        "LANDGER",
        "NAT-EXIS",
        "COM-FFM",
        "DEUFFM"
      ],
      deal_type: [
        "UNDERLYING_OTHER",
        "DHD",
        "UNDERLYING_BOOKING",
        "UNDERLYING_BC-ICICI",
        "UNDERLYING_BC-THIRDPARTY",
        "UNDERLYING_ECB-ICICI",
        "UNDERLYING_ECB-THIRDPARTY",
        "UNDERLYING_FCNR-LOAN-ICICI",
        "UNDERLYING_FLTL-ICICI",
        "UNDERLYING_EEFC",
        "UNDERLYING_FCTL-THIRDPARTY",
        "UNDERLYING_LC-ICICI",
        "UNDERLYING_LC-THIRDPARTY",
        "UNDERLYING_PCFC-ICICI",
        "UNDERLYING_PCFC-THIRDPARTY",
        "UNDERLYING_WEDL-ICICI",
        "UNDERLYING_WEDL-THIRDPARTY",
        "UNDERLYING_ECB-FN",
        "UNDERLYING_ECCB"
      ],
      trans_type: [
        "REM_GTSU",
        "REM_IIOC",
        "REM_SETTL",
        "TRAVELER_CHEAQUE",
        "TRAVEL_ATM_FEE",
        "TRAVEL_EXP",
        "TRAVEL_INC",
        "IN_FX_TC_INC",
        "IN_FX_TC_EXP",
        "IN_FX_TC_EXGAIN",
        "IN_FX_TC_EXLOSS"
      ],
      rec_corr: ["SETT-FX", "USDGTSU_HKG-GTS"]
    };
  },

  mounted() {
    this.$root.$on("pass_to_dataEntry", (buy, sell) => {
      this.buy = buy;
      this.sell = sell;
      console.log(sell);
      console.log(buy);
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.form-row {
  font-size: 13px;
}
.form-row input,
select,
option,
textarea {
  line-height: 18px;
  padding: 0;
  height: 10;
  border: none;
  color: white;
  outline: 0;
  background: transparent;
  box-shadow: none;
  border-bottom: 1px solid black;
}
.form-button {
  border: 1px solid rgb(93, 137, 168);
  text-align: center;
  line-height: 42px;

  color: white;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: 16px;
  text-rendering: auto;
  text-shadow: 0 1px 1px rgba(0, 0, 0, 0.2);
  -webkit-transition: background-color 0.4s ease;
  transition: background-color 0.4s ease;
  -webkit-border-radius: 0 4px 4px 0;
  border-radius: 0 4px 4px 0;
}

.form-button:hover {
  background-color: rgb(93, 137, 168);
  color: white;
}

.form-row {
  display: flex;
  justify-content: flex-start;
  padding: 0.2em;
}

.form-row > label {
  flex: 1;
}
.form-row > input,
.form-row > select {
  color: white;
  border-radius: 5px;

  flex: 2;
}
option {
  background-color: #e4e2e2;
  color: #646464;
}
option:hover {
  background: #5d89a8;
  color: white;
}
</style>

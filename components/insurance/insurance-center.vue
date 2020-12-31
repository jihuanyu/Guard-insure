<template>
  <div class="insurance_center">
    <div class="buy-type">
      <button
        @click="handleClickType('buy')"
        :class="type == 'buy' ? 'active' : ''"
      >
        {{ $t("Type.BuyInsurance") }}
      </button>
      <button
        @click="handleClickType('sell')"
        :class="type == 'sell' ? 'active1' : ''"
      >
        {{ $t("Type.ToInsurance") }}
      </button>
    </div>
    <CoinType
      @changeCoin="handleClickCoinType"
      :currentCoin="curCoin"
    ></CoinType>
    <Echart></Echart>
    <InsuranceType
      @changeType="handleClickTradeType"
      :currentType="TradeType"
    ></InsuranceType>
    <Balance
      :currentCoin="curCoin"
      :currentType="TradeType"
      :TradeType="type"
    ></Balance>
    <InsuranceList
      v-if="type == 'buy'"
      :currentCoin="curCoin"
      :currentType="TradeType"
    ></InsuranceList>
    <InsuranceForm
      v-if="type == 'sell'"
      :currentCoin="curCoin"
      :currentType="TradeType"
    ></InsuranceForm>
    <RePrice v-if="repriceflag" :option="option"> </RePrice>
  </div>
</template>

<script>
import CoinType from "./coin-type.vue";
import Echart from "./echart.vue";
import InsuranceType from "./insurance-type.vue";
import Balance from "./balance.vue";
import InsuranceList from "./insurance-list.vue";
import InsuranceForm from "./insurance-form.vue";
import RePrice from "./re-price.vue";
export default {
  components: {
    CoinType,
    Echart,
    InsuranceType,
    Balance,
    InsuranceList,
    InsuranceForm,
    RePrice,
  },
  data() {
    return {
      type: "buy",
      curCoin: "HELMET",
      TradeType: 1,
      repriceflag: false,
      option: {},
    };
  },
  mounted() {
    this.$bus.$on("OPEN_REPRICE", (data) => {
      this.repriceflag = true;
      this.option = data;
    });
    this.$bus.$on("CLOSE_REPRICE", () => {
      this.repriceflag = false;
    });
  },
  methods: {
    // 选择买卖类型
    handleClickType(type) {
      this.type = type;
    },
    // 选择币种类型
    handleClickCoinType(coin) {
      this.curCoin = coin;
    },
    //选择保险品种
    handleClickTradeType(type) {
      this.TradeType = type;
    },
  },
};
</script>

<style lang='scss' scoped>
@import "~/assets/css/base.scss";
@media screen and(min-width:750px) {
  .insurance_center {
    width: 1080px;
    margin: 0 auto;
    background: #fff;
    padding: 40px 60px;
  }
  .buy-type {
    background: #fff;
    width: 100%;
    display: flex;
    height: 50px;
    overflow: hidden;
    button {
      transform: skew(0 0 30px 0);
      border: none;
      outline: none;
      flex: 1;
      text-align: center;
      line-height: 50px;
      font-size: 16px;
      font-weight: bold;
      color: #121212;
      background: #f7f7fa;
      &:first-child {
        background: linear-gradient(-59deg, transparent 25px, #f7f7fa 0) top
          right;
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      &:last-child {
        background-size: 100% 100%;
        background: linear-gradient(120deg, transparent 25px, #f7f7fa 0) top
          left;

        background-repeat: no-repeat;
      }
    }
    .active {
      color: #fff;
      background: linear-gradient(-59deg, transparent 25px, #4364e8 0) top right !important;
    }
    .active1 {
      color: #fff;
      background: linear-gradient(120deg, transparent 25px, #4364e8 0) top left !important;
    }
  }
}
@media screen and(max-width:750px) {
  .insurance_center {
    margin-bottom: 10px;
    background: #fff;
    padding: 20px 16px;
  }
  .buy-type {
    background: #f7f7fa;
    width: 100%;
    display: flex;
    height: 50px;
    border-bottom: 2px solid #ff9600;
    border-radius: 3px 3px 0px 0px;
    overflow: hidden;
    button {
      border: none;
      outline: none;
      flex: 1;
      text-align: center;
      line-height: 50px;
      font-size: 16px;
      font-weight: bold;
      color: #121212;
      border-radius: 3px 3px 0px 0px;
    }
    .active {
      background: #ff9600;
      color: #fff;
    }
  }
}
</style>
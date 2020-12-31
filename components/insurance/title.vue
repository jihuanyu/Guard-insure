<template>
  <div class="trade_title">
    <img src="~/assets/img/helmet/banner_ill.png" alt="" />
    <div class="text">
      <h3>{{ $t("Banner.Title") }}</h3>
      <span>{{ $t("Banner.Text") }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style lang='scss' scoped>
.trade_title {
  height: 360px;
  background: #ffffff;
  margin-bottom: 15px;
  padding: 0 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  img {
    width: 613px;
    height: 360px;
  }
  .text {
    margin-left: 40px;
    h3 {
      font-size: 28px;
      color: #121212;
      line-height: 40px;
      margin-bottom: 20px;
    }
    span {
      color: #919aa6;
      font-size: 12px;
      line-height: 20px;
    }
  }
}
</style>
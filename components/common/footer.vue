<template>
  <div class="footer-container">
    <div class="footer_bottom">
      <p>Powered by payaso.io core team</p>
      <div class="footer_top">
        <div>
          <a href="">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-Twitter"></use>
            </svg>
          </a>
          <a href="">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-Telegram"></use>
            </svg>
          </a>
          <a href="">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-Discord"></use>
            </svg>
          </a>
          <a href="">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-medium"></use>
            </svg>
          </a>
        </div>
      </div>
      <Langauage class="langauage" />
    </div>
  </div>
</template>
<script>
import Langauage from "~/components/common/langauage.vue";
import "~/assets/svg/iconfont.js";
export default {
  props: ["padding"],
  name: "p-footer",
  components: { Langauage },
};
</script>
<style lang="scss" scoped>
@import "~/assets/css/base.scss";
@media screen and (min-width: 750px) {
  .footer-container {
    width: 100%;
    height: 80px;
    background: #fff;
    display: flex;
    min-width: 1200px;
    box-sizing: border-box;
    .footer_top {
      flex: 1;
      display: flex;
      justify-content: flex-end;
      div {
        width: 216px;
        display: flex;
        justify-content: space-between;
        margin-right: 80px;
        a {
          display: flex;
          flex-direction: column;
          align-items: center;
          img {
            width: 24px;
            height: 24px;
          }
          span {
            margin-top: 4px;
            font-size: 14px;
            color: #787878;
          }
        }
      }
    }
    .footer_bottom {
      padding: 0 6.25vw;
      width: 100%;
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      display: flex;
      background: #f5f7fb;
      p {
        font-size: 14px;
        font-weight: 400;
        color: #919aa6;
      }
    }
  }
}
@media screen and (min-width: 750px) and (max-width: 1280px) {
  .footer_bottom {
    padding: 0 50px !important;
  }
}

@media screen and (max-width: 750px) {
  .footer-container {
    width: 100%;
    height: 176px;
    display: flex;
    flex-direction: column;
    background: #f5f7fb;
    .footer_top {
      width: 100%;
      margin-top: 40px;
      div {
        display: flex;
        justify-content: space-between;
        width: 200px;
        a {
          display: flex;
          flex-direction: column;
          align-items: center;
          img {
            width: 24px;
            height: 24px;
          }
          span {
            margin-top: 4px;
            font-size: 14px;
            color: #787878;
          }
        }
      }
    }
    .footer_bottom {
      margin-top: 30px;
      width: 100%;
      height: 176px;
      display: flex;
      align-items: center;
      flex-direction: column;
      padding: 0 16px !important;
      display: flex;
      p {
        width: 100%;
        font-size: 14px;
        font-weight: 400;
        color: #919aa6;
      }
      .langauage {
        display: none;
      }
    }
  }
}
.icon {
  width: 24px;
  height: 24px;
  vertical-align: -0.15em;
  fill: #787878;
  overflow: hidden;
}
.footer_top {
  a:hover {
    .icon {
      fill: #4364e8;
    }
    span {
      color: #4364e8 !important;
    }
  }
}
</style>
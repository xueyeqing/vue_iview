<template>
  <div class="layout" :class="{'layout-hide-text': spanLeft < 4}">
    <div class="layout-ceiling">
      <div class="layout-ceiling-main">
        <a href="#">注册登录</a> |
        <a href="#">帮助中心</a> |
        <a href="#">安全中心</a> |
        <a href="#">服务大厅</a>
      </div>
    </div>
    <i-row class="layout-row" type="flex">
      <!--left-->
      <i-col :span="spanLeft" class="layout-menu-left">
        <i-menu class="layout-menu-leftmenu" active-name="1" width="auto">
          <div class="layout-logo-left">
            <i-icon class="layout-logo-leftimg" type="ios-keypad" :size="imgSize"></i-icon>
          </div>
          <i-menu-item name="1">
            <i-icon type="ios-navigate" :size="iconSize"></i-icon>
            <span class="layout-text">选项 1</span>
          </i-menu-item>
          <i-menu-item name="2">
            <i-icon type="ios-keypad" :size="iconSize"></i-icon>
            <span class="layout-text">选项 2</span>
          </i-menu-item>
          <i-menu-item name="3">
            <i-icon type="ios-analytics" :size="iconSize"></i-icon>
            <span class="layout-text">选项 3</span>
          </i-menu-item>

          <i-submenu name="4">
            <template slot="title">
              <i-icon type="ios-navigate" :size="iconSize"></i-icon>
              <span class="layout-text">导航一</span>
            </template>
            <i-menu-item name="1-1">选项 一</i-menu-item>
            <i-menu-item name="1-2">选项 二</i-menu-item>
            <i-menu-item name="1-3">选项 三</i-menu-item>
          </i-submenu>

          <i-submenu name="5">
            <template slot="title">
              <i-icon type="ios-keypad" :size="iconSize"></i-icon>
              <span class="layout-text">导航二</span>
            </template>
            <i-menu-item name="2-1">选项 一</i-menu-item>
            <i-menu-item name="2-2">选项 二</i-menu-item>
            <i-menu-item name="2-3">选项 三</i-menu-item>
          </i-submenu>

        </i-menu>
      </i-col>
      <!--right-->
      <i-col :span="spanRight">
        <div class="layout-header">
          <Button type="text" @click="toggleClick">
            <Icon type="navicon" size="32"></Icon>
          </Button>
        </div>
      </i-col>

    </i-row>

  </div>
</template>

<script>
  export default {
    data () {
      return {
        spanLeft: 4,
        spanRight: 20,
      }
    },
    computed: {
      iconSize () {
        return this.spanLeft === 4 ? 14 : 24;
      },
      imgSize() {
        return this.spanLeft === 4 ? 60 : 45;
      }
    },
    methods: {
      toggleClick () {
        if (this.spanLeft === 4) {
          this.spanLeft = 2;
          this.spanRight = 22;
        } else {
          this.spanLeft = 4;
          this.spanRight = 20;
        }
      }
    }
  }
</script>

<style lang="less" rel="stylesheet/less" scoped>

  @import "../style/variables.less";

  .layout {
    border: 1px solid @divider;
    background: #f5f7f9;
    position: relative;
    overflow: hidden;
    width: 100%;
    height: 100%;
  }

  .layout-ceiling {
    background: @corlor-write;
    padding: 10px 0;
    overflow: hidden;
    border-bottom: 1px solid @divider;
  }

  .layout-ceiling-main {
    float: right;
    margin-right: 15px;
  }

  .layout-ceiling-main a {
    color: #424242;
  }

  .layout-row {
    height: 100%;
  }

  .layout-header {
    height: 60px;
    background: @corlor-write;
    box-shadow: 0 1px 1px rgba(0, 0, 0, .1);
  }

  .layout-menu-left {
    /*height: 100%;*/
  }

  .layout-menu-leftmenu {
    height: 100%;
  }

  .layout-logo-left {
    height: 120px;
    background: @corlor-write;
    text-align: center;
  }

  .layout-logo-leftimg {
    height: 120px;
    line-height: 120px;
  }

  .layout-hide-text .layout-text {
    display: none;
  }

</style>

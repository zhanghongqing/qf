<template>
  <div class="wrapper" @click="update">
    <image :src="logoUrl" class="logo"></image>
    <text class="title">Hello {{target}}</text>
    <text class="desc">Now, let's use vue to build your weex app.</text>
    <div class="d1"><text>1</text></div>
    <div class="d2"><text>2</text></div>
    <wxc-button text="Open Popup"
      @wxcButtonClicked="buttonClicked">
    </wxc-button>
    <wxc-popup width="500"
      pos="left"
      :show="isShow"
      @wxcPopupOverlayClicked="overlayClicked">
    </wxc-popup>
    <TabNav />
  </div>
</template>

<script>
  import { WxcButton, WxcPopup } from 'weex-ui';
  import Header from './components/Header.vue'
  import TabNav from './components/TabNav.vue'
  export default {
    data: () => ({
      logoUrl: 'http://img1.vued.vanthink.cn/vued08aa73a9ab65dcbd360ec54659ada97c.png',
      target: 'World',
      isShow: false
    }),
    components: { WxcButton, WxcPopup, Header, TabNav },
    methods: {
      update: function (e) {
        this.target = 'Weex'
        console.log('target:', this.target)
      },
      buttonClicked () {
        this.isShow = true;
      },
      overlayClicked () {
        this.isShow = false;
      }
    }
  }
</script>

<style>
  .wrapper { align-items: center; margin-top: 120px; }
  .d1 {width: 700px;height: 100px;background-color: #eee;border-width: 10px;border-style: solid;border-color: #000;}
  .d2 {width: 100px;height: 100px;background-color: red;}
  .title { padding-top:40px; padding-bottom: 40px; font-size: 48px; }
  .logo { width: 360px; height: 156px; }
  .desc { padding-top: 20px; color:#888; font-size: 24px;}
</style>

<template>
  <div class="container">
    <wxc-minibar title="标题"
     background-color="#009ff0"
     text-color="#FFFFFF"
     right-text="更多"
     @wxcMinibarLeftButtonClicked="minibarLeftButtonClick"
     @wxcMinibarRightButtonClicked="minibarRightButtonClick"></wxc-minibar>
  </div>
</template>

<script>
  import { WxcMinibar } from 'weex-ui';
  const modal = weex.requireModule('modal')
  export default {
    components: { WxcMinibar },
    methods: {
      minibarLeftButtonClick () {
        console.log(12314)
      },
      minibarRightButtonClick () {
        modal.toast({ 'message': 'click rightButton!', 'duration': 1 })
      }
    }
  }
</script>

<style>

</style>

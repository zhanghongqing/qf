<template>
  <div id="index">
    <div class="body" :style="{ height: bodyHegiht }">
      <TabNav />
    </div>
  </div>
</template>

<script>
  import TabNav from './components/TabNav.vue'
  import QfHeader from './components/QfHeader.vue'
  import { Utils } from 'weex-ui';
  export default {
    data: () => ({
      bodyHegiht: '0px'
    }),
    components: { TabNav, QfHeader, Utils },
    created () {
      const tabPageHeight = Utils.env.getPageHeight();
      console.log(tabPageHeight, Utils.env.getScreenHeight())
      this.bodyHegiht = `${tabPageHeight}px`
      console.log('.............................', Utils)
    },
    methods: {
      init () {
        console.log('init')
      }
    }
  }
</script>


<style lang="scss">
  @import './index.scss'
</style>

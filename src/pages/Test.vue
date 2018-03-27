<template>
  <div id="index">
    <text>123141241</text>
  </div>
</template>

<script>
  import { Utils } from 'weex-ui';
  export default {
    data: () => ({
      bodyHegiht: '0px'
    }),
    components: { Utils },
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

</style>

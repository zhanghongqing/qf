<template>
  <wxc-tab-bar :tab-titles="tabTitles"
               :tab-styles="tabStyles"
               title-type="icon"
               @wxcTabBarCurrentTabSelected="wxcTabBarCurrentTabSelected">
    <!-- 第一个页面内容-->
    <div class="item-container" @click="jump" :style="contentStyle">
      <text>{{index}}</text>
      <div class="btn" @click="jump">跳转啊</div>
      <a href="/dist/pages/Test.web.js"><text>跳跳</text></a>
    </div>

    <!-- 第二个页面内容-->
    <div class="item-container" :style="contentStyle"><text>特别推荐</text></div>

    <!-- 第三个页面内容-->
    <div class="item-container" :style="contentStyle"><text>消息中心</text></div>

    <!-- 第四个页面内容-->
    <div class="item-container" :style="contentStyle"><text>我的主页</text></div>
  </wxc-tab-bar>
</template>

<script>
  import { WxcTabBar, Utils } from 'weex-ui';
  let navigator = weex.requireModule('navigator')

  // https://github.com/alibaba/weex-ui/blob/master/example/tab-bar/config.js 
  import Config from './config'

  export default {
    components: { WxcTabBar },
    data: () => ({
      tabTitles: Config.tabTitles,
      tabStyles: Config.tabStyles,
      index: '首页'
    }),
    created () {
      const tabPageHeight = Utils.env.getPageHeight();
      // 如果页面没有导航栏，可以用下面这个计算高度的方法
      // const tabPageHeight = env.deviceHeight / env.deviceWidth * 750;
      const { tabStyles } = this;
      this.contentStyle = { height: (tabPageHeight - tabStyles.height) + 'px' };
    },
    methods: {
      jump () {
        var params = {'url': '/dist/pages/Test.js','animated':'true'}
        navigator.push(params, function(e) {
          console.log('i am the callback.')
        });
      },
      wxcTabBarCurrentTabSelected (e) {
        const index = e.page;
        // console.log(index);
      }
    },
    mounted () {
      console.log(12314124124124151)
    }
  }
</script>

<style scoped>
  .item-container {
    width: 750px;
    background-color: #f2f3f4;
    align-items: center;
    justify-content: center;
  }
  .btn{
    width: 100px;
    height: 100px;
    background-color: #aaa;
  }
</style>

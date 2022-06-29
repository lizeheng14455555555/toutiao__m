<template>
    <div class="qa-container">
          <div class="haeaaa"> 设置</div>
        <div class="main">
 <div class="div1">
  <van-cell title="账号与安全" is-link to="/index" />

        </div>
        <div class="div1"> 
    <van-cell title="青少年模式" is-link to="/index" />
     <van-cell title="关怀模式" is-link to="/index" />
        </div>
        <div class="div1"> 
      <van-cell title="新消息通知" is-link to="/my" />
       <van-cell title="通用" is-link to="/index" />
     <van-cell title="聊天" is-link to="/index" />
        </div>
      <span class="sp"> 隐私</span>  
          <div class="div1"> 
      <van-cell title="朋友权限" is-link to="/index" />
       <van-cell title="个人信息与权限" is-link to="/index" />
     <van-cell title="个人信息收集清单" is-link to="/index" />
          <van-cell title="第三方信息共享清单" is-link to="/index" />
        </div>

         <div class="div1"> 
      <van-cell title="关于微信" is-link to="/index" />
       <van-cell title="帮助与反馈" is-link to="/index" />
        </div>
        <div class="div1"> 
      <van-cell title="插件" is-link to="/index" />
     
        </div>
          <div class="div1"> 
     <van-button type="default" class="but">切换帐号</van-button>
        </div>
          <div class="div1"> 
      <van-button type="default" class="but">退出</van-button>
        </div>
        </div>
    
    </div>
    
</template>

		<script>
export default {
    name: 'QaPage',
    components: {},
    props: {},
    data() {
        return {
            arr:[{
                name:'刘海龙'
            },
            {
                name:'杨文涵'
            },
            {
                name:'郑福景'
            },
            {
                name:'杨智博'
            },
            {
                name:'赵成博'
            },
             {
                name:'赵成博'
            },
             {
                name:'赵成博'
            },
             {
                name:'赵成博'
            },
          ]
        }
    },
    computed: {},
    watch: {},
    created() { },
    mounted() { },
    methods: {}
}
</script>

<style scoped>
  .haeaaa{
    width: 100%;
    height: 80px;
    position: fixed;
    top: 0px;
   z-index: 10;
 text-align: center;
 line-height: 80px;
 font-size:36px ;
  background-color: white;
  }
  .div1{
    margin-bottom: 10px;
  }
 .sp{
    font-size: 14px;
    padding-left: 15px;
 }
 .but{
    width: 100%;
 }
 .main{
      padding-top: 80px;
    padding-bottom: 120px;
 }
</style>
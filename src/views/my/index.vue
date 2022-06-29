<template>
  <div class="my-container">

   
     <van-nav-bar
  title=" 新消息通知"
  left-text="返回"
  right-text="按钮"
  left-arrow
  @click-left="onClickLeft"
  @click-right="onClickRight"
/>
     <div class="main">
 <div class="div1"> 
  <van-cell center title="接受新消息通知">
  <template #right-icon>
    <van-switch v-model="checked" size="24" />
  </template>
</van-cell>
     <van-cell center title="接受语音和视频通话邀请提醒">
  <template #right-icon>
    <van-switch v-model="checked1" size="24" />
  </template>
</van-cell>
        </div>

<div class="div1"> 
  <van-cell center title="通知显示消息详情">
  <template #right-icon>
    <van-switch v-model="checked2" size="24" />
  </template>
</van-cell>
    
        </div>
 <span class="sp">声音与震动</span>  
 <div class="div1"> 
 <van-cell title="新消息系统通知" is-link value="前往系统通知设置" />
 <van-cell title="语音和视频通话提醒" is-link value="前往系统通知设置" />

        </div>
         <span class="sp">提示音与铃声</span> 
        <div class="div1"> 
         
 <van-cell title="新消息系统通知" is-link value="跟随系统" />
 <van-cell title="来电铃声" is-link />


        </div>
           <span class="sp">跟新提示</span> 
           <div class="div1">
          <van-cell center title="朋友">
  <template #right-icon>
    <van-switch v-model="checked7" size="24" />
  </template>
</van-cell>
<van-cell center title="视频号">
  <template #right-icon>
    <van-switch v-model="checked8" size="24" />
  </template>
</van-cell>
<van-cell center title="直播">
  <template #right-icon>
    <van-switch v-model="checked9" size="24" />
  </template>
</van-cell>
<van-cell center title="附近">
  <template #right-icon>
    <van-switch v-model="checked10" size="24" />
  </template>
</van-cell>
          </div>
         </div>
  </div>
</template>
<script>
export default {
  name: "MyPage",
  components: {},
  props: {},
  data() {
    return {
      
      checked: false,
       checked1: false,
        checked2: false,
         checked7: false,
       checked8: false,
        checked9: false,
         checked10: false,
    };
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {
      onClickLeft() {
      this.$router.go(-1)
    },
  },
};
</script>

<style scoped>
.div1{
    margin-bottom: 10px;
  }
  .main{
      padding-top: 80px;
    padding-bottom: 120px;
 }
 
  .sp{
    font-size: 14px;
    padding-left: 15px;
 }
</style>

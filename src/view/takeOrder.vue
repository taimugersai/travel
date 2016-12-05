<template>
  <div class="wrap">
    <div class="content"  v-for="item in lists">
        <img src="../../static/head5.png">
        <div class="info">
          <p class="name">12345游客</p>
          <p class="time right">2016-12-12-12:00</p>
          <p class="words">哪哪真的是一个好地方，哪哪真的是一个好地方，哪哪真的是一个好地呀 哪哪真的是一个好地方，哪哪真的是一个好地方，哪哪真的是一个好地呀 哪哪真的是一个好地方，哪哪真的是一个好地呀  哪哪真的是一个好地方，哪哪真的是一个好地呀    </p>
        </div>
        <div class="empty"></div>
    </div>
  </div>
</template>
<script>
import Vue from 'vue'

export default {
  components: {
   
  },
  data: function () {
    return {
      lists:[{question:"如果遇到坏天气怎么办？",time:"2016-12-12-12:00",answer:"如果遇到这种情况我们会这么处理这件事情，不会造成 你的损失。"},
      {question:"如果时间错过了？",time:"2016-12-12-12:00",answer:"如果遇到这种情况我们会这么处理这件事情，不会造成 你的损失。"},
      {question:"如果半路有事怎么处理？",time:"2016-12-12-12:00",answer:"如果遇到这种情况我们会这么处理这件事情，不会造成 你的损失。"},
      {question:"如果半路有事怎么处理？",time:"2016-12-12-12:00",answer:"如果遇到这种情况我们会这么处理这件事情，不会造成 你的损失。"},]
    }
  },
  mounted: function() {
    
  },
  methods: {
    
  }
}
</script>
<style lang="less" scoped>
@import '../assets/css/common.less';
.wrap{
  height:100vh;
  background:@bgColor;
  .content{
    padding:0 (6.4rem-@mainWidth)/2;
    padding-bottom:0.16rem;
    background:white;
    height:1.54rem;
    margin-bottom:0.21rem;
    img{
      float:left;
      display:inline-block;
      width:0.66rem;
      height:0.66rem;
      border-radius:0.33rem;
      margin-top:0.3rem;
    }
    .info{
      display:inline-block;
      width:4.7rem;
      height:1.57rem;
      margin-left:0.03rem;
      .name{
        display:inline-block;
        color:#383434;
        font-size:0.214rem;
        margin-top:0.25rem;
        margin-left:0.11rem;
      }
      .time{
        margin-top:0.28rem;
      }
      .words{
        font-size:0.157rem;
        margin-top:0.09rem;
        margin-left:0.05rem;
        line-height:0.29rem;
        color:#524d4d;
        display: -webkit-box;
           -webkit-box-orient: vertical;
           -webkit-line-clamp: 3;
           overflow: hidden;
      }
    }
  }
}
</style>
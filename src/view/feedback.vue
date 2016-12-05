<template>
  <div class="wrap">
    <div class="content"  v-for="item in lists">
        <img src="../../static/question.png" >
        <p class="question">{{item.question}}</p>
        <p class="time">{{item.time}}</p>
        <img src="../../static/answer.png" style="float:left;margin-top:0.23rem">
        <p class="answer">{{item.answer}}</p>
        <div class="empty"></div>
    </div>
    <div class="ask">用户提问</div>
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
    background:white;
    height:2.2rem;
    margin-bottom:0.21rem;
    img{
      display:inline-block;
      width:0.4rem;
      height:0.4rem;
      margin-top:0.15rem;
    }
    .question{
      display:inline-block;
      line-height:0.4rem;
      margin-left:0.2rem;
      height:0.4rem;
      font-size:0.318rem;
      color:#060606;
      position:relative;
      top:-0.07rem;
    }
    .time{
      display:block;
      margin-left:0.65rem;
      font-size:0.214rem;
    }
    .answer{
      position:relative;
      top:0.28rem;
      width:5rem;
      display:inline-block;
      margin-left:0.2rem;
      font-size:0.214rem;
    }
  }
  .ask{
        position: fixed;
        bottom:0;
        left:0;
        background:@base;
        color:white;
        height:0.86rem;
        width:100%;
        text-align:center;
        line-height:0.86rem;
        font-size:0.28rem;
      }
}
</style>
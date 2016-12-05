<template>
  <div class="wrap">
  <div class="content">
    <div class="detail_box" v-for="(item, index) in detail" >
            <div class="empty" v-if="index!=0"></div>
            <div style="position:relative">
            <img v-lazy="item.img"  class="bg_img"/>
            <p class="name">{{item.name}}</p>
            <div class="del right">删除</div>
            <p class="info gray">{{item.info}}</p>
            <p class="right" style="margin-top:0.25rem;">
              <span class="base" style="font-size:0.39rem;font-weight:bold;font-family:'微软雅黑';">￥{{item.price}}元</span>
              <span class="gray" style="font-size:0.26rem;">/人</span><span class="gray" style="font-size:0.22rem;">起</span>
            </p>
            <p>
              <span class="tag" v-for="tags in item.tags">{{tags}}</span>
            </p>
            <!-- 图片上的半透明标签 -->
            <div class="img_tag">
              <p class="img_tag_top">{{item.size}}</p>
              <p class="img_tag_bottom">{{item.address}}</p>
            </div>
          </div>
    </div>
   </div>
  </div>
</template>
<script>



export default {
  components: {
   
  },
  data: function () {
    return {
     detail:[{"id":1,"stars":4,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/router1.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房","TOP5景点","大巴"],"class":"hot","address":"黄山","size":"50人团"},
        {"id":2,"stars":4,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟....","price":195,"img":"static/router2.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房","TOP5景点","大巴"],"class":"hot","address":"黄山","size":"50人团"},
        {"id":3,"stars":4,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg3.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房","TOP5景点","大巴"],"class":"专线特惠","address":"黄山","size":"50人团"},
        {"id":4,"stars":3,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg2.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房"],"class":"专线特惠","address":"黄山","size":"50人团"},
        {"id":5,"stars":2,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg2.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房"],"class":"名俗风情","address":"黄山","size":"50人团"},
        {"id":6,"stars":1,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg3.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房","TOP5景点","大巴"],"class":"古都韵味","address":"黄山","size":"50人团"},
        {"id":7,"stars":5,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房","TOP5景点","大巴"],"class":"西部风情","address":"黄山","size":"50人团"},
        {"id":8,"stars":5,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg.png","tags":["豪华海景房","TOP5景点","大巴","豪华海景房","TOP5景点","大巴"],"class":"浪漫海滨","address":"黄山","size":"50人团"},
        {"id":8,"stars":5,"name":"惠山古镇一日游惠山古镇一日游","info":"全年畅销，美食街特惠供应，机跟团游全年 畅销，美食街特惠供应，机跟团游机跟团游机跟团游机跟团游机跟团游.","price":200,"img":"static/detailbg3.png","tags":["豪华海景房","TOP5景点"],"class":"专线特惠","address":"黄山","size":"50人团"}

      ]
    }
  },
  methods: {
  }
}
</script>
<style lang="less" scoped>
@import '../assets/css/common.less';
.wrap{
   background:white;
  .content{
    width:@mainWidth;
    margin-left:(6.4-@mainWidth)/2;
  }
}
.detail_box{
    width:100%; 
    padding-top:0.32rem;
    margin-bottom:0.19rem;
    border-bottom:1px solid #ebebeb;
    .bg_img{
      width:100%;
      height:2.41rem;
    }
    .name{
      width:60%;
      font-size:@fontBig;
      margin-top:0.1rem;
      color:#454545;
      overflow:hidden;
      text-overflow: ellipsis;
      white-space:nowrap;
      display:inline-block;
    }
    .del{
      background:@base;
      color:white;
      width:0.58rem;
      height:0.29rem;
      border-radius:3px;
      text-align:center;
      font-size:0.16rem;
      margin-top:0.11rem;
     
    }
    .info{
      width:59.2%;
      height:0.63rem;
      font-size:@fontSize;
      margin-top:0.1rem;
      margin-bottom:0.17rem;
      line-height:@lineHeight;
      overflow:hidden;
      text-overflow: ellipsis;
      display:inline-block;
    }
    .tag{
      display:inline-block;
      border:1px solid @base;
      color:@base;
      font-size:@fontSmall;
      padding:0px 5px;
      margin-right:0.14rem;
      margin-bottom:0.2rem;
      border-radius:3px;
    }
    .empty{
      width:100vw;
      margin-left:-(6.4-@mainWidth)/2;
      height:0.21rem;
      background:#ebebeb;
      margin-bottom:0.36rem;
    }
    //图片上的半透明标签
    .img_tag{
      width:0.92rem;
      height:0.7rem;
      color:white;
      position:absolute;
      right:0.26rem;
      top:1.46rem;
      text-align:center;
      over-flow:hidden;
      .img_tag_top{
        height:0.4rem;
        line-height:0.4rem;
        background:rgba(238,105,37,0.84);
        border-top-left-radius:6px;
        border-top-right-radius:6px;
        font-size:@fontSmall;
      }
      .img_tag_bottom{
        height:0.3rem;
        line-height:0.35rem;
        background:rgba(56,45,23,0.84);
        border-bottom-left-radius:6px;
        border-bottom-right-radius:6px;
        font-size:0.167rem;
        font-weight:bold;
      }
    }
  }
</style>
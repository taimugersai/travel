<template>
  <div class="wrap">
    <!-- 头部介绍 -->
    <header>
      <div class="h-figure">
        <img :src="detail.headImg" alt="">
        <router-link to="/"><img class="back" src="../assets/images/back_icon.png" alt=""></router-link>
      </div>
      
      <div class="h-intro">
        <p class="h-title">{{ detail.title }}</p>
        <p><span class="h-price">￥{{ detail.price }}元</span><span style="font-size:.28rem;">/人</span>起</p>
        <p class="h-describe">
          {{ detail.intro }}
        </p>
      </div>
    </header>

    <div class="group">
      <p>出发地<span style="margin-left:10px;">{{ detail.address }}</span></p>
    </div>

    <!-- 出发日期 -->
    <div class="group">
      <p>出发日期<span class="text-small gray">（以下均为起价）</span></p>
      <div class="content clear">
        <div class="layout left" v-for="item in detail.time">
          <p class="gray">{{ item.date }}</p>
          <p class="base">￥{{ item.price }}/人</p>
        </div>
      </div>

    </div>

    <!-- 评论 -->
    <div class="group">
      <p>线路评论<span class="text-small gray right"> 共{{ detail.comment.num }}条 >></span></p>
      <div class="content border-bottom">
        <div class="comment" v-for="item in detail.comment.user">
          <div class="c-head">
            <div class="head-icon left">
              <img :src="item.head_url" alt="">
            </div>
            <div class="c-user">
              <p class="c-name">{{ item.name }}</p>
              <p class="text-small gray">{{ item.date }}</p>
            </div>
          </div>
          <div class="c-body">
            {{ item.content }}
          </div>
        </div>
      </div>
      <div class="more-btn">查看全部</div>
    </div>

    <!-- 线路特色 -->
    <div class="group">
      <p>线路特色</p>
      <ul class="content c-list">
        <li>晚连住180度海景房，更有升级酒店可供选择，各具特色！</li>
        <li>经典行程，96%高满意度，明星导游带队，去了都说不错！</li>
        <li>升级专车接机，晚航班再也不用怕啦</li>
      </ul>
    </div>

    <!-- 参考行程 时间轴 -->
    <div class="group">
      <p>参考行程</p>
      <ul class="content">
        <li v-for="(item, index) in color">
          <timeline :color="item" :sub="days[index]" :step="index" title="出发地厦门">
            <div>
              <img v-if="img[index]" :src="img[index]" alt="">
                8:00~8:30  中央公园大巴集合
                早餐：敬请自理
                午餐：豪华海鲜大餐
                晚餐：烧烤派对
                住宿：厦门（大床/标间）
            </div>
          </timeline>
          <!-- <div class="timeline clear">
            <div class="t-left">
              <p :style="{color:item}">
                <span class="text-large bold">{{(index+1)<10 ? '0'+(index+1) : (index+1)}}</span><br>
                <span class="text-small">{{ days[index] }}</span><br>
                <span class="dot" :style="{backgroundColor:item}"></span>
              </p>
            </div>
            <div class="t-right">
              <p class="text-big t-title">出发地厦门</p>
              <div class="t-content">
                <img v-if="img[index]" :src="img[index]" alt="">
                8:00~8:30  中央公园大巴集合
                早餐：敬请自理
                午餐：豪华海鲜大餐
                晚餐：烧烤派对
                住宿：厦门（大床/标间）
              </div>
            </div>
          </div> -->
        </li>
      </ul>
    </div>

    <!-- 出行须知 -->
    <div class="group">
      <p>出行须知</p>
      <div class="content">
        <div class="g-column">
          <div class="g-title">
            <span class="iconfont bold">&#xe6c3;</span>费用包含：
          </div>
          <div class="g-container">
            往返团队/散客机票含税费（团队机票将统一出票，散客机票因实时计价预定后即刻出票）当地旅游巴士
            中间段船票(鼓浪屿轮渡往返船票)
          </div>
        </div>
        <div class="g-column">
          <div class="g-title">
            <span class="iconfont bold">&#xe6c3;</span>费用不包含：
          </div>
          <div class="g-container">
            往返团队/散客机票含税费（团队机票将统一出票，散客机票因实时计价预定后即刻出票）当地旅游巴士
            中间段船票(鼓浪屿轮渡往返船票)
          </div>
        </div>
      </div>
    </div>

    <!-- 特别提醒 -->
    <div class="group">
      <p>特别提醒</p>
      <div class="content">
        <div class="g-column">
          <div class="g-title">
            <span class="iconfont bold">&#xe6c3;</span>购物说明：
          </div>
          <div class="g-container">
            往返团队/散客机票含税费（团队机票将统一出票，散客机票因实时计价预定后即刻出票）当地旅游巴士
            中间段船票(鼓浪屿轮渡往返船票)
          </div>
        </div>
        <div class="g-column">
          <div class="g-title">
            <span class="iconfont bold">&#xe6c3;</span>注意事项：
          </div>
          <div class="g-container">
            往返团队/散客机票含税费（团队机票将统一出票，散客机票因实时计价预定后即刻出票）当地旅游巴士
            中间段船票(鼓浪屿轮渡往返船票)
          </div>
        </div>
      </div>
    </div>

    <div class="h12 bg-white"></div>

    <div class="footer">
      <div class="f-left">
        <div class="f-tips">
          <span class="iconfont text-large">&#xe70d;</span><br>
          <span class="text-small">客服</span>
        </div>
        <div class="f-tips" @click="collect">
          <span class="iconfont text-large">{{ isCollect ? '&#xe605;' : '&#xe60d;' }}</span><br>
          <span class="text-small">收藏</span>
        </div>
      </div>
      <div class="f-right">
        下一步
      </div>
    </div>

  </div>
</template>

<script>
import { http } from '../xhr'
import Timeline from '../components/timeline/timeline'

export default {
  components: {
   Timeline
  },
  mounted () {
    
  },
  data: function () {
    return {
      isCollect: false,
      img: [
        'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3399122602,2145564046&fm=116&gp=0.jpg',
        '',
        'https://ss0.baidu.com/73x1bjeh1BF3odCf/it/u=1716604723,2407555611&fm=85&s=91145E94FC5716DEBA29690C030070C2',
        '',
        'http://img4.imgtn.bdimg.com/it/u=2464392702,1411032928&fm=21&gp=0.jpg',
        '',
        'https://ss0.baidu.com/73x1bjeh1BF3odCf/it/u=1716604723,2407555611&fm=85&s=91145E94FC5716DEBA29690C030070C2',
        '',
        'http://img4.imgtn.bdimg.com/it/u=2464392702,1411032928&fm=21&gp=0.jpg',
        '',
      ],
      days: ['Day One','Day Two','Day Three','Day Four','Day Five','Day Six','Day Seven','Day Eight','Day Nine','Day Ten'],
      color: ['#f95b1d', '#7f80ae', '#ef4136', '#2b3991', '#00a79d', '#f95b1d', '#7f80ae', '#ef4136', '#2b3991', '#00a79d'],
      detail: {
        headImg: '/static/head.jpg',
        title: '惠山古镇一日游',
        intro: '全年畅销，美食街特惠供应，机跟团游全年畅销，美食街特惠全年畅销，美食街特惠供应，机跟团游全年畅销，美食街特惠全年畅销，美食街特惠供应，机跟团游全年畅销，美食街特惠',
        price: 200,
        address: '无锡',
        time: [{
          date: '11-27 周四',
          price: 1250
        },{
          date: '11-27 周四',
          price: 1250
        },{
          date: '11-27 周四',
          price: 1250
        },{
          date: '11-27 周四',
          price: 1250
        },{
          date: '11-27 周四',
          price: 1250
        },{
          date: '11-27 周四',
          price: 1250
        }],
        comment: {
          num: 213,
          user: [{
            date: '2016-10-05',
            name: '小羊咩咩米',
            head_url: './static/head.png',
            content: '生于南方长于南方对海的印象永远处于想象中，蔚蓝无边，帆船遨游，海鸥盘旋。生于南方长于南方对海的印象永远处于想象中，蔚蓝无边，帆船遨游，海鸥盘旋。生于南方长于南方对海的印象永远处于想象中，蔚蓝无边，帆船遨游，海鸥盘旋。'
          },{
            date: '2016-10-05',
            name: '这个人很懒',
            head_url: './static/head2.png',
            content: '满意，满意，很满意!!!重要的事情说三遍，哈哈，我绝不是托哈生于南方长于南方对海的印象永远处于想象中...。'
          }]
        }
      }
    }
  },
  methods: {
    collect () {
      this.isCollect = !this.isCollect;
    }
  }
}
</script>
<style lang='less'>
@import '../assets/css/common.less';
@import '../assets/css/detail.less';
</style>
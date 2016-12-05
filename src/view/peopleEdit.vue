<template>
  <div class="wrap">
    <div class="header">
    <router-link to="/user">
       <img src="../../static/cancel.png" class="cancel" >
    </router-link>
       <p>编辑出行人信息<span>保存</span></p>
    </div>
    <div class="content">
      <div class="list">
        <p class="list_left">证件类型</p>
        <p class="right"><span :class="active=='身份证'?'orange':''" @click="shengcenzheng">身份证</span>/<span :class="active=='护照'?'orange':''" @click="huzhao">护照</span></p>
      </div>
      <div class="list" v-if="active=='护照'">
        <p class="list_left">国籍</p>
        <input  type="text" :placeholder="country"></input>
      </div>
      <div class="list">
        <p class="list_left">证件号</p>
        <input  type="number" :placeholder="idNumber"></input>
      </div>
      <div class="list">
        <p class="list_left">姓名</p>
        <input  type="text" :placeholder="name"></input>
      </div>
      <div class="list">
        <p class="list_left">手机号码</p>
        <input  type="number" :placeholder="phoneNumber"></input>
      </div>
      <p class="connection">紧急联系人</p>
      <div class="list">
        <p class="list_left">姓名</p>
        <input  type="text" :placeholder="connectName"></input>
      </div>
      <div class="list">
        <p class="list_left">手机号码</p>
        <input  type="number" :placeholder="connectPhonerNumber"></input>
      </div>
      <div class="del">删除出行人</div>
    </div>
  </div>
</template>
<script>
import Vue from 'vue'
import { Switch } from 'mint-ui';
import 'mint-ui/lib/switch/style.css';
Vue.component(Switch.name, Switch);


export default {
  components: {
   
  },
  data: function () {
    return {
     active:"身份证",
     country:"中国",
     idNumber:"123456789012345678",
     name:"韩梅梅",
     phoneNumber:"12312332123",
     connectName:"韩梅梅",
     connectPhonerNumber:"123321112321"
    }
  },
  mounted: function() {
    
  },
  methods: {
    shengcenzheng:function(){
      this.active="身份证"
    },
    huzhao:function(){
      this.active="护照"
    }
  }
}
</script>
<style lang="less" scoped>
@import '../assets/css/common.less';
.wrap{
  background:white;
}
.header{
  background:#eeeeee;
  width:6.4rem;
  height:0.86rem;
  border-bottom:1px solid #c8c8c8;
  .cancel{
    width:0.18rem;
    height:0.18rem;
    margin-top:0.34rem;
    margin-left:0.2rem
  }
  p{
    display:inline-block;
    color:black;
    font-size:0.28rem;
    margin-left:1.8rem;
    span{
      font-size:0.24rem;
      margin-left:1.53rem
    }
  }
}
.content{
  height:9.6rem;
  background:white;
  .list{
    width:6rem;
    height:0.99rem;
    border-bottom:2px solid #dadada ; 
    margin-left:0.2rem;
    font-size:0.24rem;
    color:black;
    line-height:0.99rem;
    .list_left{
      display:inline-block;
      width:1rem;
      margin-left:0.04rem;
    }
    input{
      width:4rem;
      margin-left:0.8rem;
      text-align:right;
      font-size:0.24rem;
      color:black;
      font-family:"Microsoft Yahei"
    }
  }
  .connection{
    text-align:center;
    font-size:0.28rem;
    color:black;
    margin-top:0.23rem;
    margin-bottom:0.23rem;
  }
  .del{
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
.orange{
  color:@base
}
      :-moz-placeholder { /* Mozilla Firefox 4 to 18 */
          font-family:"Microsoft Yahei";
          color: #000; opacity:1; 
      }

      ::-moz-placeholder { /* Mozilla Firefox 19+ */
        font-family:"Microsoft Yahei";
          color: #000;opacity:1;
      }

      input:-ms-input-placeholder{
        font-family:"Microsoft Yahei";
          color: #000;opacity:1;
      }

      input::-webkit-input-placeholder{
        font-family:"Microsoft Yahei";
          color: #000;opacity:1;
      }
</style>
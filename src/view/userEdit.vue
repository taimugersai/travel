<template>
  <div class="wrap">
    <div class="content">
      <div class="list" style="height:1.43rem;line-height:1.43rem;border-top:0">
        <p class="list_left">头像</p>
        <div class="right"> 
        <input type="file"  accept="image/*" id="upload" hidden @change="upload"></input>
           <label for="upload" >
              <div style="height:1rem">
              <img :src="img" alt="">      
              </div>  
          </label>
        </div>
      </div>
      <div class="list">
        <p class="list_left">昵称</p>
        <input  type="number" :placeholder="name"></input>
      </div>
      <div class="list">
        <p class="list_left">手机号码</p>
        <input  type="number" :placeholder="phoneNumber"></input>
      </div>
      <div class="empty"></div>
      <div class="list" style="border-top:0">
        <p class="list_left">个性签名</p>
        <input  type="text" :placeholder="words"></input>
      </div>
      <div class="save">保存</div>
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
      img:"../../static/head3.png",
     name:"旅行者",
     phoneNumber:"12312332123",
     userIcon:"../../static/head3.png",
     words:"加油 加油"
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
    },
    upload:function(e){
       let upload = e.target.files[0];
           
       var url = window.URL.createObjectURL(upload);
console.log(url)
this.img=url;
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
  background:white;
  .list{
    width:6rem;
    height:0.99rem;
    border-top:2px solid #dadada ; 
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
      color:@textColor;
      font-family:"Microsoft Yahei"
    }
    img{
      width:1rem;
      height:1rem;
      margin-top:0.18rem;
      margin-right:0.03rem;
    }
    
  }
 .empty{
      width:6.4rem;
      height:0.4rem;
      background:#ebebeb
    }
  .save{
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
          
      }

      ::-moz-placeholder { /* Mozilla Firefox 19+ */
        font-family:"Microsoft Yahei";
          
      }

      input:-ms-input-placeholder{
        font-family:"Microsoft Yahei";
          
      }

      input::-webkit-input-placeholder{
        font-family:"Microsoft Yahei";
          
      }
</style>
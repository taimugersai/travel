<template>
  <div class="wrap">
   <div class="list" v-for="(item, index) in lists">
     <p class="name">{{item.name}}</p>
     <div class="page-tab-container">
      <mt-tab-container class="page-tabbar-tab-container right" v-model="active[index]" swipeable>
        <mt-tab-container-item id="tab-container1">
          <router-link to="/peopleEdit"><p class="edit">编辑</p></router-link>
        </mt-tab-container-item>
        <mt-tab-container-item id="tab-container2">
          <p class="del">删除</p>
        </mt-tab-container-item>
      </mt-tab-container>
    </div>
   </div>
  </div>
</template>
<script>
import Vue from 'vue'

import { TabContainer, TabContainerItem } from 'mint-ui';

Vue.component(TabContainer.name, TabContainer);
Vue.component(TabContainerItem.name, TabContainerItem);


export default {
  components: {
   
  },
  data: function () {
    return {
     active: [],
     lists:[{id:1,name:"韩梅梅"},{id:2,name:"韩梅梅"},{id:3,name:"韩梅梅"},{id:4,name:"韩梅梅"},{id:5,name:"韩梅梅"},]
    }
  },
  mounted: function() {
    for(var i=0;i<this.lists.length;i++){
      this.active.push("tab-container1")
    }
    console.log(this.active)
  },
  methods: {
  }
}
</script>
<style lang="less" scoped>
@import '../assets/css/common.less';
.list{
  width:100vw;
  height:0.84rem;
  background:white;
  margin-bottom:0.07rem;
  line-height: 0.84rem;
  .name{
    display:inline-block;
    color:black;
    font-size:0.24rem;
    margin-left:0.5rem;
  }
  .edit{
    width:1.3rem;
    color:@base;
    font-size:0.24rem;
  }
  .del{
    width:1.3rem;
    color:white;
    font-size:0.24rem;
    background:@base
  }
  .mint-tab-container{
    width:1.3rem;
    text-align:center;
    position: relative;
    top:-0.84rem;
  }
}
</style>
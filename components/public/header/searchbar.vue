<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col 
        :span="3"
        class="left">
        <img 
          src="http://s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png" 
        >
      </el-col>
      <el-col 
        :span="15"
        class="center">
        <div class="wrapper">
          <el-input 
            v-model="search"
            placeholder="搜索商家或地点"
            @focus="focus"
            @blur="blur"/>
          <button class="el-button el-button--primary">
            <i class="el-icon-search"/>
          </button>
          <dl
            v-if="isHotPlace" 
            class="hotPlace">
            <dt>热们搜索</dt>
            <dd>火锅</dd>
            <dd>火锅</dd>
            <dd>火锅</dd>
            <dd>火锅</dd>
          </dl>
          <dl 
            v-if="isSearchList"
            class="searchList">
            <dd>炒面</dd>
            <dd>炒面</dd>
            <dd>炒面</dd>
            <dd>炒面</dd>
            <dd>炒面</dd>
          </dl>
        </div>
        <p class="suggest">
          <a href="#">雪中悍刀行</a>
          <a href="#">雪中悍刀行</a>
          <a href="#">雪中悍刀行</a>
          <a href="#">雪中悍刀行</a>
          <a href="#">雪中悍刀行</a>
        </p>
        <ul class="nav">
          <li>
            <nuxt-link 
              to="/"
              class="takeout"
            >剑来</nuxt-link>
          </li>
          <li>
            <nuxt-link 
              to="/"
              class="movie"
            >剑来</nuxt-link>
          </li>
          <li>
            <nuxt-link 
              to="/"
              class="hotel"
            >剑来</nuxt-link>
          </li>
          <li>
            <nuxt-link 
              to="/"
              class="apartment"
            >剑来</nuxt-link>
          </li>
          <li>
            <nuxt-link 
              to="/"
              class="business"
            >剑来</nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col 
        :span="6"
        class="right">
        <ul class="security">
          <li><i class="refund"/><p class="txt">随时退</p></li>
          <li><i class="single"/><p class="txt">不满意免单</p></li>
          <li><i class="overdue"/><p class="txt">过期退</p></li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>
<script>
export default {
  data(){
    return{
      // 判断是否有内容
      search:'',
      // 判断是否聚焦
      isFocus: false
    }
  } ,
   computed:{
      isHotPlace(){return this.isFocus && !this.search}       
      ,
      isSearchList(){return this.isFocus && this.search}        
    } ,
    methods:{
      focus(){this.isFocus = true },          
      blur(){
        setTimeout(() => {
          this.isFocus = false
        }, 200);  
      }
    }
};
</script>
<style lang="scss">
</style>
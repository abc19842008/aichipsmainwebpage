<template>
  <div class="top">
    <div class="index">
      <div class="logo">
        <img src="~@/assets/logo.png" alt="">
        <p>中山市爱芯科技有限公司</p>
      </div>
      <div class="nav-box">
        <span v-for="item in nav" :key="item.name"
              :class="{active:isChecked(item)}" @click="navClick(item.path)">{{item.name}}</span>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "index",
    data(){
      return{
        nav:[
          {
            name:'首页',
            path:'/home'
          },
          {
            name:'关于我们',
            path:'/about'
          },
          {
            name:'产品中心',
            path:'/product'
          },
          /*
          {
            name:'案例中心',
            path:'/project'
          },
          */
          {
            name:'联系我们',
            path:'/contact'
          },
        ]
      }
    },
    methods:{
      isChecked(item){
        return !item.path.indexOf(this.$route.path)
      },
      navClick(path){
        this.$router.push(path)
      }
    },
  }
</script>

<style scoped>
  .top{
    display: flex;
    justify-content: center;
    background-color: #FAFAFA;
    width: 100%;
  }
  .index{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 1200px;
    height: 112px;
  }
  .logo{
    display: flex;
    align-items: center;
  }
  .logo img{
    height: 60px;
    width: 60px;
    margin-right: 10px;
  }
  .nav-box{
    width: 500px;
    display: flex;
    font-size: 16px;
    justify-content: space-evenly;
  }
  .nav-box span{
    /*不同浏览器的渐变效果*/
    -webkit-transition: all .5s;
    -moz-transition: all .5s;
    -o-transition: all .5s;
    transition: all .5s;
  }
  .nav-box :hover{
    color: #3a8ee6;
    cursor:pointer;
  }
  .active{
    color: #3a8ee6;
  }

</style>

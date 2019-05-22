<template>
  <div class="mui-row">
    <div class="mui-col-xs-12 mui-row nav">
      <div class="mui-col-xs-4" @tap="tab1=1;tab2=1;tab3=1">
        <router-link to="/recommend" ><img :src="'img/tabIcon/tab1'+tab1+'.png'" @tap="tab1=1;tab2=1;tab3=1"/><span class="mui-tab-label" @tap="tab1=1;tab2=1;tab3=1">{{"推荐好课" | title}}</span></router-link>
      </div>
      <div class="mui-col-xs-4" @tap="tab2=2;tab1=2;tab3=1">
        <router-link :to="{path: '/Broadcast/' +(tabNum=tabNum==undefined?0:tabNum)}"><img :src="'img/tabIcon/tab2'+tab2+'.png'" @tap="tab2=2;tab1=2;tab3=1"/><span class="mui-tab-label" @tap="tab2=2;tab1=2;tab3=1">{{"师道直播" | title}}</span></router-link>
      </div>
      <div class="mui-col-xs-4" @tap="tab3=2;tab1=2;tab2=1">
        <router-link to="/my"><img :src="'img/tabIcon/tab3'+tab3+'.png'" @tap="tab3=2;tab1=2;tab2=1"/><span class="mui-tab-label" @tap="tab3=2;tab1=2;tab2=1">{{"我" | title}}</span></router-link>
      </div>
    </div>
  </div>
</template>
<style scoped>
  .mui-row { background: #FFF; border-top:1px solid #F5F5F5; }
  .mui-col-xs-12 .mui-col-xs-4 { text-align: center; height: 50px; }
  img{position:relative; top:0px; width: 30px; height: 30px; padding-top: 0; padding-bottom: 0; }
  .mui-tab-label{ font-size: 11px; display: block; overflow: hidden; text-overflow: ellipsis; margin-top: -7px; }
  a{color:#b9b5b5;}
  .mui-bar{ -webkit-box-shadow: 0 0 1px rgba(222, 219, 219, 0.85); box-shadow: 0 0 1px rgba(222, 219, 219, 0.85); }
  .mui-row .router-link-exact-active.router-link-active{ color:#3FCDFF; }
  .mui-col-xs-12 .mui-col-xs-4 a{height: 50px; display: inline-block; width: 100%;}
</style>
<script>
  export default {
    created() {
      this.$route.params.tabNum=0;
    },
    mounted() {
      if(this.$route.params.tabNum!='undefined'){
        this.tabNum=this.$route.params.tabNum;//因为这个切换选项卡就path改变了
      }
      else{
        this.tabNum=0;
      }
      if(this.$route.path=='/my'){
        this.tab3=2;this.tab1=2;this.tab2=1
      }
      else if(this.$route.path=='/Broadcast/'+this.tabNum){//因为这里的path是随着选项卡切换改变的。所以要写成动态的。
        this.tab2=2;this.tab1=2;this.tab3=1
      }else{
        this.tab1=1;this.tab2=1;this.tab3=1
      }

    },
    beforeRouteEnter(to, from, next) {
      // console.log(to)
      //   if (to.params.db == null) {
      //     return next({ name: "", params: { id: to.params.id } });
      //   }
      //   next();
    },
    components: {},
    data() {
      return {
        tabNum:0,
        tab1:1,
        tab2:1,
        tab3:1,
      }
    },
    methods: {
    },
    watch:{
      '$route.params'(tab){ //
        this.tabNum=this.$route.params.tabNum;
      },
    }
  }
</script>

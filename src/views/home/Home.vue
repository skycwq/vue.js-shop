<template>
  <div>
    <nav-bar class="home-nav"><div slot="content" >购物街</div></nav-bar>
    <home-swiper :banners='banners'></home-swiper>
    <Recomment :recomments='recommends'></Recomment>
  </div>
</template>

<script>
import NavBar from '@/components/common/navbar/NavBar'
import HomeSwiper from './swiper/HomeSwiper'

import Recomment from './children/Recomment'
import { getHomeMultidata } from '@/network/home.js'

export default {
    name:'Home',
    components:{
      NavBar,
      HomeSwiper,
      Recomment
    },
    data(){
      return {
        banners:[],
        recommends:[]
        
      }
    },
   created(){
     getHomeMultidata().then(
       res=>{
        this.banners=res.data.banner.list
        this.recommends=res.data.recommend.list
       
       }
     )
   }
}

</script>
<style>
.home-nav{
  background-color: orangered;
  color: #fff;
}
</style>
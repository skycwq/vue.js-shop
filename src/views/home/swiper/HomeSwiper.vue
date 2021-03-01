<template>
  <div>
    <swiper :options="swiperOptions">
      <div class="swiper-slide" :key="index" v-for="(item, index) in banners">
        <a :href="item.link">
          <img :src="item.image" />
        </a>
      </div>

      <div class="swiper-pagination" slot="pagination"></div>
      <!-- 左右箭头 -->
      <!-- <div class="swiper-button-prev swiper-button-black" slot="button-prev"></div>
      　　
      <div class="swiper-button-next swiper-button-black" slot="button-next"></div> -->
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  data() {
    return {
      swiperOptions: {
       loop: true,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
       
        autoplay: {
          delay: 3000,
          // stopOnLastSlide:false,
          // reverseDirection:false
        },
        
        // navigation: {
        //   nextEl: ".swiper-button-next",
        //   prevEl: ".swiper-button-prev",
        // },
    
      },
    };
  },
  props: {
    banners: {
      type: Array,
      defaults: [],
    },
  },
};
</script>
<style>
img {
  width: 100%;
}
</style>
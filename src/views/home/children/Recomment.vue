<template>
  <div class="recomment">
      <div class="recomment-item" v-for="(item, index) in recomments" :key="index">
          <a :href="item.link">
              <img :src="item.image" alt="">
              <div >{{item.title}}</div>
          </a>
      </div>
  </div>
</template>

<script>
export default {
    name:'Recomment',
    props:{
        recomments:{
            type:Array,
            dataults:[]
        }
    }
}

</script>
<style>
.recomment{
    display: flex;
    padding-bottom: 35px;
    border-bottom: 8px solid rgb(238, 234, 234);
}
.recomment .recomment-item{
    flex: 1;
    text-align: center;
    padding: 10px 0 20px 0;
}
.recomment .recomment-item img{
    width: 80px;
    padding-bottom: 8px;
}
.recomment .recomment-item div{
    font-size: 15px;
}
</style>
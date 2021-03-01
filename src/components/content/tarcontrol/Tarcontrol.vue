<template>
  <div class="tracontrol">
    <div class="tracontrol-item" v-for="(item, index) in titles" :key="index" :class='{active:currect===index}' @click='itemColor(index)'>
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Tarcontrol",
  data(){
      return {
          currect:0
      }
  },
  props: {
    titles: {
      types: Array,
      defaults: [],
    }
  },
  methods:{
      itemColor(index){
          this.currect=index
      }
  }
};
</script>
<style>
.tarcontrol{
    display: flex;
    text-align: center;
    height: 44px;
    line-height: 44px;
}
.tracontrol-item{
    flex: 1;
    font-size: 16px;
}
.active span{
    padding: 5px;
    border-bottom: 3px solid #ff4500;
}
.active{
    color: #ff4500;
}
</style>
<template>
  <div>
       <div id="tab-bar">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
 name:'TabBar',
 components:{
    //    TabBarItem
 }
}

</script>
<style>
#tab-bar{
   display: flex;
   position: fixed;
   left: 0;
   bottom: 0;
   right: 0;
}

</style>
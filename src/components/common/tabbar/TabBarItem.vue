<template>
  <div class="tab-bar-item" @click="itemclick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>

    <div v-else><slot name="item-icon-active"></slot></div>

    <div :style="activeStyle"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
export default {
  name: "TarBarItem",
  props: {
    path: {
      type: String,
    },
    activeColor: {
      type: String,
      default: "red",
    },
  },
  data() {
    return {
      // isActive:true
    };
  },
  computed: {
    isActive() {
      return this.$route.path.includes(this.path);
    },

    activeStyle() {
      return this.isActive ? { color: this.activeColor } : {};
    },
  },
  methods: {
    itemclick() {
      this.$router.replace(this.path);
    },
  },
};
</script>
<style>
.tab-bar-item {
  flex-grow: 1;
  height: 49px;
  background: #f2f2f2;
  box-shadow: 0px -3px 0px 0px rgba(0, 0, 0, 0.02);
  text-align: center;
}
.tab-bar-item img {
  height: 24px;
  width: 24px;
  vertical-align: middle;
  margin-top: 3px;
}
</style>
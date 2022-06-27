<template>
  <div class="my-tab-bar">
    <div
      :class="[`tab-item`, { current: currentChoose === index }]"
      v-for="(item, index) in goodsChoose"
      :key="index"
      @click="chooseBtn(index, item.componentName)"
    >
      <!-- 图标 -->
      <span :class="`iconfont ${item.iconText}`"></span>
      <!-- 文字 -->
      <span>{{ item.text }}</span>
    </div>
  </div>
</template>

<script>
/**
 * @author
 * 思路：点击后让页面切换   子传父(父做事)
 */
export default {
  props: {
    goodsChoose: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      currentChoose: 0
    }
  },
  methods: {
    chooseBtn(index, tagName) {
      this.currentChoose = index
      this.$emit('change-tagname', tagName)
    }
  }
}
</script>

<style lang="less" scoped>
.my-tab-bar {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 50px;
  border-top: 1px solid #ccc;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: white;
  .tab-item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

.current {
  color: #1d7bff;
  .iconfont {
    color: #1d7bff;
  }
}
</style>

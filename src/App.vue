<template>
  <div class="remember">
    <MyHeader
      background="rgba(68, 68, 68)"
      title="Apple"
      color="rgba(255, 255, 255)"
    ></MyHeader>
    <component :is="chooseName"></component>
    <MyFooter
      :goodsChoose="tabList"
      @change-tagname="changeTageName"
    ></MyFooter>
  </div>
</template>

<script>
import MyHeader from '#/MyHeader.vue'
import MyFooter from '#/MyFooter.vue'
import MyGoodsList from '@/views/MyGoodsList.vue'
import MyGoodsSearch from '@/views/MyGoodsSearch.vue'
import MyUserInfo from '@/views/MyUserInfo.vue'
export default {
  components: {
    MyHeader,
    MyFooter,
    MyGoodsList,
    MyGoodsSearch,
    MyUserInfo
  },
  data() {
    return {
      chooseName: 'MyGoodsList',
      tabList: [
        {
          iconText: 'icon-shangpinliebiao',
          text: '商品列表',
          componentName: 'MyGoodsList'
        },
        {
          iconText: 'icon-sousuo',
          text: '商品搜索',
          componentName: 'MyGoodsSearch'
        },
        {
          iconText: 'icon-user',
          text: '我的信息',
          componentName: 'MyUserInfo'
        }
      ]
    }
  },
  methods: {
    changeTageName(tagName) {
      this.chooseName = tagName
    }
  }
}
</script>

<style scoped>
.remember {
  padding: 50px 0;
}
</style>

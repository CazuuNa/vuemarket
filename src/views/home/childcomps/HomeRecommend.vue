<template>
  <div class="home-recommend">
    <div class="home-recommend-item" v-for="item in crecommends">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
  export default {
    name: "HomeRecommend",
    props: {
      crecommends: {
        type: Array,
        default() {
          return []
        }
      }
    },
    methods:{
      // filterT4() {
      //   return this.cproducts.slice(0,4)
      // }
    }
  }
</script>

<style scoped>
  .home-recommend{
    display: flex;
    width: 100%;
    text-align: center;
    padding: 5px;
    border-bottom: 10px solid #eee;
  }
  .home-recommend-item{
    flex: 1;
  }
  .home-recommend-item img{
    width: 70px;
    height: 65px;
    border-radius: 100%;
  }
</style>

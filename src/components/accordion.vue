<template>
  <div>
    <ul class="imgBox">
      <li class="item" :class="{'activeImg':index===activeIndex}" v-for="(item,index) in imgList" :key="index" @mouseover="changeIndex(index)">
        <img :src="item.src" alt="" height="225" width="300">
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      activeIndex: 0,
      imgList: [
        {id: 1, src: require('../assets/img/han1.jpg')},
        {id: 2, src: require('../assets/img/han2.jpg')},
        {id: 3, src: require('../assets/img/han3.jpg')},
        {id: 4, src: require('../assets/img/han4.jpg')},
        {id: 5, src: require('../assets/img/han5.jpg')}
      ]
    }
  },
  methods: {
    changeIndex (index) {
      this.activeIndex = index
    }
  }
}
</script>

<style scoped lang="scss">
.imgBox{
  width: 900px;
  overflow: hidden;
}
.item{
  width: 150px;
  height: 225px;
  overflow: hidden;
  float: left;
  >img{
    width: 300px !important;
  }
}
.activeImg{
  width: 300px !important;
  transition: all 0.3s;
  animation: changeImg 0.2s linear;
}
@keyframes changeImg {
  0%{
    width: 200px;
  }
  100%{
    width: 300px !important;
  }
}
</style>

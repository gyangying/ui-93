<template>
<div class='container'>
  <my-slider
    :auto="2000"
    :list="list"
    :curIdx="curIdx"
    style="height:200px;width:350px"
    @click="hClick"
  ></my-slider>
</div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
      curIdx: 1,
      list: [
        { url: require('./img/1.jpg'), alt: '1.肖申克的救赎' },
        { url: require('./img/2.jpg'), alt: '2.肖申克的救赎' },
        { url: require('./img/3.jpg'), alt: '3.肖申克的救赎' },
        { url: require('./img/4.jpg'), alt: '4.肖申克的救赎' },
        { url: require('./img/5.jpg'), alt: '5.肖申克的救赎' }
      ]
    }
  },
  methods: {
    hClick (idx) {
      console.log(idx + '被点了')
    }
  }
}
</script>

<style scoped lang='less'></style>

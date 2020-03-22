<template>
<div class='container'>
  <h1>测试my-dialog</h1>
  <button type="primary" @click="isShow !== isShow">切换显示</button>
  <my-dialog v-model="isShow"></my-dialog>
</div>
</template>

<script>
export default {
  name: 'page-dialog',
  data () {
    return {
      isShow: false
    }
  }
}
</script>

<style scoped lang='less'></style>

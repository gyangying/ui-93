<template>
<div class='container'>
  <h1>测试my-dialog</h1>
  <button type="primary" @click="isShow = !isShow">切换显示</button>
  <my-dialog
    v-model="isShow"
    title="简历真难写"
    content="确实难写">
    <div slot="body">
      <p>1</p>
      <p>2</p>
      <p>3</p>
    </div>
    </my-dialog>
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

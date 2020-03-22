<template>
  <div class="ui divider horizontal header">
    <!-- 有icon就显示icon图标，显示图标有默认类icon，动态定义类icon -->
    <i v-if="icon" class="icon" :class="icon"></i>
    <slot>我是默认内容</slot>
  </div>
</template>

<script>
export default {
  name: 'divider',
  props: {
    icon: {
      type: String,
      default: '',
      require: false
    }
  }
}
</script>

<style scoped lang='less'></style>

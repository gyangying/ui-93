<template>
  <div class="ui dimmer modals page active" :class="{'active':isShow}">
    <div class="ui standard modal active" :class="{'active':isShow}" style="top: 60px;">
      <i class="close icon" @click="hNo"></i>
      <div class="header">头部</div>
      <div class="content">
        <div class="description">内容</div>
      </div>
      <div class="actions">
        <div class="ui black button">Nope</div>
        <div class="ui positive right labeled icon button">
          Yep, that's me
          <i class="checkmark icon"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'my-dialog',
  props: {
    value: {
      type: Boolean,
      required: false,
      default: false
    }
  },
  data () {
    return {
      isShow: this.value
    }
  },
  watch: {
    value () {
      console.log('v-model值变了', this.value)
      this.isShow = this.value
    }
  },
  methods: {
    hNo () {
      // 子组件
      this.isShow = false
      // 父组件
      this.$emit('input', this.isShow)
    }
  }
}
</script>

<style scoped lang='less'></style>

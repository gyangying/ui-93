<template>
  <div class="ui dimmer modals page" :class="{'active':isShow}">
    <div class="ui standard modal" :class="{'active':isShow}" style="top: 60px;">
      <i class="close icon" @click="hNo"></i>
      <div class="header">
        <slot name="header">{{title}}</slot>
      </div>
      <div class="content">
        <div class="description">
          <slot name="body">{{content}}</slot>
        </div>
      </div>
      <div class="actions">
        <div class="ui black button" @click="nope">{{noTxt}}</div>
        <div class="ui positive right labeled icon button" @click="yes">
          {{yesTxt}}
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
    },
    title: {
      type: String,
      default: '系统提示',
      require: false
    },
    content: {
      type: String,
      default: '加油！',
      require: false
    },
    noTxt: {
      type: String,
      default: '取消',
      require: false
    },
    yesTxt: {
      type: String,
      default: '确定',
      require: false
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
    },
    nope () {
      this.hNo()
      this.$emit('no')
    },
    yes () {
      this.hNo()
      this.$emit('yes')
    }
  }
}
</script>

<style scoped lang='less'></style>


  <!-- <div>
    <h2 class="ui huge header" :class="size">
      <i v-if="icon" class="icon" :class="icon"></i>
      <div class="content">
        <slot>默认内容</slot>
        <div class="sub header">
          <slot name="sub"></slot>
        </div>
      </div>
    </h2>
  </div> -->

<script>
export default {
  name: 'MyHeadline',
  props: {
    level: {
      type: Number,
      default: 1,
      required: false
    },
    icon: {
      type: String,
      default: '',
      required: false
    },
    size: {
      type: String,
      default: 'medium',
      required: false
    }
  },
  data () {
    return {

    }
  },
  render (h) {
    let icon = null
    let content = null
    if (this.icon) {
      // <i class="settings icon"></i>
      icon = h('i', { class: 'icon ' + this.icon })
    }
    if (this.$slots.sub) {
      // 是有副标题的
      // 创建副标题
      const subContent = h('div', { class: 'sub header' }, [this.$slots.sub])
      // 内容包含两个部分：默认插槽 + 具名插槽
      content = h('div', { class: 'content' }, [this.$slots.default, subContent])
    } else {
      content = h('div', { class: 'content' }, [this.$slots.default])
    }

    return h('h' + this.level, { class: 'ui ' + this.size + ' header' }, [icon, content])
  }
}
</script>

<style lang="" scoped>

</style>

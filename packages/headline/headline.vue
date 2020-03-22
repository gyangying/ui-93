
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
      icon = h('i', { class: 'icon' + this.icon })
    }
    if (this.$slots.sub) {
      const subContent = h('div', { class: 'sub header' }, [this.$slots.sub])
      content = h('div', { class: 'content' }, [this.$slots.default, subContent])
    } else {
      content = h('div', { class: 'content' }, [this.$slots.default])
    }

    return h('h' + this.level, { class: 'ui header' + this.size }, [icon, content])
  }
}
</script>

<style lang="" scoped>

</style>

<template>
  <div>
    <button  class="ui button" :class="cClass" @click="hEmitClick">
      <template v-if="animated">
        <div v-if="$slots.hidden" class="hidden content">
          <slot name='hidden'></slot>
        </div>
        <div v-if="$slots.visible" class="visible content">
          <slot name='visible'></slot>
        </div>
      </template>
      <template v-else>
        <!-- 传入图标才会显示，否则不显示图标 -->
        <i v-if="icon" class="user icon "></i>
        <slot>我是默认内容</slot>
        <!-- <slot>我是一个按钮</slot> -->
      </template>
    </button>
  </div>
</template>

<script>
export default {
  name: 'MyButton',
  data () {
    return {}
  },
  props: {
    size: {
      type: String,
      default: 'medium',
      // 校验
      vilidator (val) {
        return ['mini', 'tiny', 'small', 'medium', 'large', 'big', 'huge', 'massive'].includes(val)
      }
    },
    icon: {
      type: String,
      required: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    loading: {
      type: Boolean,
      default: false
    },
    animated: {
      type: String,
      default: ''
    }
  },
  computed: {
    cClass () {
      var classArr = [this.size]
      this.animated && classArr.push(`animated ${this.animated}`)
      this.loading && classArr.push('loading')
      this.disabled && classArr.push('disabled')
      return classArr.join(' ')
    }
  },
  methods: {
    hEmitClick () {
      this.$emit('click')
    }
  }
}
</script>

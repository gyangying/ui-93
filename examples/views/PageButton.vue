<template>
  <div class="about">
    <h1>This is an about page</h1>
    <my-button>点个赞</my-button>
    <br />
    <MyButton></MyButton>
    <br />
    <MyButton :size="size">mini</MyButton>
    <br />
    <MyButton size="huge">huge</MyButton>
    <br />
    <MyButton icon="user">icon</MyButton>
    <br />
    <MyButton disabled>disabled</MyButton>
    <br />
    <MyButton icon="history" loading>icon为history的loading按钮</MyButton>
    <br />
    <!-- 动画效果1 -->
    <my-button animated="vertical">
      <div slot="hidden">$10000</div>
      <div slot="visible">
        <i class="shop icon"></i>不要错过哈
      </div>
    </my-button>
    <br />
    <!-- 动画效果2 -->
    <my-button animated="fade">
      <div slot="hidden">$10000</div>
      <div slot="visible">
        <i class="shop icon"></i>不要错过哈
      </div>
    </my-button>
    <br>
    <MyButton @click="hClick">click事件</MyButton>
    <br />
  </div>
</template>
<script>
export default {
  data () {
    return {
      size: 'mini'
    }
  },
  methods: {
    hClick () {
      window.alert(1)
    }
  }
}
</script>

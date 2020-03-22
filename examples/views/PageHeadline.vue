<template>
<div class='container'>
  <h1>测试my-headline</h1>
  <my-headline :level="1" icon="user" size="huge">
    <slot></slot>
    <div>
      子标题111
    </div>
  </my-headline>
  <my-headline :level="2" icon="settings" size="tiny">
    标题
  </my-headline>
  <my-headline :level="2" icon="settings" size="tiny">
    标题
    <div slot="sub">
      子标题222
    </div>
  </my-headline>
</div>
</template>

<script>
export default {}
</script>

<style scoped lang='less'></style>

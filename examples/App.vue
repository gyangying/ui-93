<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/PageButton">测试按钮</router-link> |
      <router-link to="/PageDivider">测试分隔条</router-link> |
      <router-link to="/PageSlider">测试轮播图</router-link> |
      <router-link to="/PageHeadline">测试PageHeadline</router-link> |
      <router-link to="/PageDialog">测试PageDialog</router-link> |
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

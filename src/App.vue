<script setup>
import {RouterLink, RouterView} from 'vue-router'</script>
<template>
  <div id="header">
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <RouterLink to="/lineChart">LineChart.vue</RouterLink>
    </nav>
  </div>
  <div id="content">
    <RouterView/>
  </div>

</template>

<style scoped>
#header {
  height: 30px;
  display: flex;
  justify-content: center;
}

#content {
  height: calc(100vh - 30px);
  display: flex;
}
</style>

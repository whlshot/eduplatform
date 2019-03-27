<template>
  <div id="app">
    <leftNav></leftNav>
    <div class="main">
      <router-view/>
    </div>
  </div>
</template>

<script>
import leftNav from '@/components/common/LeftNav'
export default {
  name: 'App',
  components: {
    leftNav
  }
}
</script>

<style>
.main{
  float: left;
  width: 95%;
  height: 800px;
  overflow: auto;
}
</style>

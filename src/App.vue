<template>
  <HomeVue></HomeVue>
  
</template>

<script>
import { Menu as IconMenu, Message, Setting } from '@element-plus/icons-vue'

import HomeVue from './components/Home.vue';
export default {
  components: {
    HomeVue,
  }
}
</script>

<style>
#app,html,body{
  height: 100vh;
}
</style>

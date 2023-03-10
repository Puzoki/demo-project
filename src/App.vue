<template>
  <div class="container fuild-set">
    <keep-alive>
      <component :is="component" style="width: 90%"></component>
    </keep-alive>
  </div>
</template>

<script>
  import tasks from './components/tasks.vue'
  import qrcode from './components/qrcode.vue'

  export default {
    name: '#app',
    components: {
      qrcode,
      tasks,
    },
    data() {
      return {
        component: 'qrcode'
      }
    },
  }
</script>

<style scoped>
  
</style>

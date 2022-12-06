<template>
  <div id="app">
    <PageBody />
  </div>
</template>

<script>
import PageBody from '@/components/PageBody.vue'
// import PlayList from '@/components/PlayList.vue'
// import SongList from '@/components/SongList.vue'

export default {
  name: 'App',
  components: {
    PageBody,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img {
  height: 20vh;
}
</style>

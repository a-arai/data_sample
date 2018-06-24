<template>
  <main id="app">
    
      <list-item></list-item>
    
  </main>
</template>

<script>
//子コンポーネント
import ListItem from './list-item.vue';

export default {
  components: {
    //子コンポーネント登録
    'list-item': ListItem
  }
};
</script>

<style>
#app {
  color: #2c3e50;
  margin-top: 60px;
}
</style>

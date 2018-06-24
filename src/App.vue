<template>
  <main id="app">
    
      <list-item v-bind:val=search_list></list-item>
    
  </main>
</template>

<script>
//import Vue from 'vue';
import store from './store.js';

//子コンポーネント
import ListItem from './list-item.vue';

export default {
  data() {
    return {
      //JSONのデータを格納
      search_list: []
    };
  },
  components: {
    //子コンポーネント登録
    'list-item': ListItem
  },
  created() {
    //JSON取得
    store.get_ajax('', 'search_list');
    //JSON取得後に呼び出される
    store.$on('GET_AJAX_COMPLETE', () => {
      this.search_list = store.get_data('search_list');
    });
  }
};
</script>

<style>
#app {
  color: #2c3e50;
  margin-top: 60px;
}
</style>

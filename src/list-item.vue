<template>
    <ul>
        <li v-for="item in this.search_list"><span>{{ item.id }}</span><span class="urlText">{{ item.html_url }}</span></li>
    </ul>
</template>


<script>
//import Vue from 'vue';
import store from './store.js';


export default {
  data() {
    return {
      //JSONのデータを格納
      search_list: []
    };
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
li {
    margin: 10px;
    border: 1px solid #000;
    list-style: none;
    text-align: left;
    padding: 10px 20px;
    width: 700px;  
}
.urlText {
    color: #ff0000;
    padding-left: 20px;
}
</style>
<template>
    <ul>
        <li v-for="item in val"><span>{{ item.id }}</span><span class="urlText">{{ item.html_url }}</span></li>
    </ul>
</template>

<script>
export default {
  props: ['val']
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
<template>
  <div id="app">
    <nav>
       <NewsItem :newsmax="newsmax"></NewsItem>
       <PagenatiList v-model="page" :count="countProducts" :per-page="productsPerPage"></PagenatiList>
    </nav>
    <router-view/>
  </div>
</template>


<script>

import NewsItem from "./components/NewsItem.vue";
import newsmax from "./data/index";
import PagenatiList from "./components/PagenatiList.vue";

export default {
  components:{
    NewsItem,
    PagenatiList
  },

  data(){
    return{
      page:1,
      productsPerPage:4,
    }
  },

  computed:{
   newsmax(){
     const offset = (this.page - 1) * this.productsPerPage;
     return newsmax.slice(offset, offset + this.productsPerPage);
   },
   countProducts(){
     return newsmax.length;
   }
 }

}
</script>
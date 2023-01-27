<template>
    <NotionRenderer :blockMap="blockMap" :blockTable="blockTable" fullPage />
    <!-- <NotionRenderer :blockMap="blockMap" :blockTable="blockTable"></NotionRenderer> -->
  </template>
  
  <script>
  import { getPageBlocks, NotionRenderer } from "vue-notion";
  
  export default {
    components: { NotionRenderer },
    data: () => ({ blockMap: null, fullPage:null }),
  
    async created() {
      // get Notion blocks from the API via a Notion pageId
      this.blockMap = await getPageBlocks("12bcd0e4f56d481c8c50f51b83929bf6");
    },
  
  };
  </script>
  
  <style>
  @import "vue-notion/src/styles.css"; /* optional Notion-like styles */
  </style>
  
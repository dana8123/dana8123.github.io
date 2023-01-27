<template>
    <NotionRenderer :blockMap="blockMap" :blockTable="blockTable" fullPage />
  </template>
  
  <script>
  import { getPageBlocks, NotionRenderer } from "vue-notion";
  
  export default {
    components: { NotionRenderer },
    data: () => ({ blockMap: null, fullPage:null }),
  
    async created() {
      // get Notion blocks from the API via a Notion pageId
      this.blockMap = await getPageBlocks("b49ebd94518d48ae934b82acb2e8d1ec");
    },
  
  };
  </script>
  
  <style>
  @import "vue-notion/src/styles.css"; /* optional Notion-like styles */
  </style>
  
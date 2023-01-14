<template>
    <NotionRenderer :blockMap="blockMap" :blockTable="blockTable" fullPage />
    <!-- <NotionRenderer :blockMap="blockMap" :blockTable="blockTable"></NotionRenderer> -->
  </template>
  
  <script>
  import { getPageBlocks, NotionRenderer, getPageTable } from "vue-notion";
  // kafka
  export default {
    components: { NotionRenderer },
    data: () => ({ blockMap: null, fullPage:null }),
  
    async created() {
      // get Notion blocks from the API via a Notion pageId
      this.blockMap = await getPageBlocks("d46ece1b435c41d593cf1709a939741e");
    },
  
  };
  </script>
  
  <style>
  @import "vue-notion/src/styles.css"; /* optional Notion-like styles */
  </style>
  
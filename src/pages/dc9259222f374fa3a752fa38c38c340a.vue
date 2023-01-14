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
      this.blockMap = await getPageBlocks("dc9259222f374fa3a752fa38c38c340a");
    },
  
  };
  </script>
  
  <style>
  @import "vue-notion/src/styles.css"; /* optional Notion-like styles */
  </style>
  
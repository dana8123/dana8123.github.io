<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
  <NotionRenderer :blockTable="blockTable"></NotionRenderer>
</template>

<script>
import { getPageBlocks, getPageTable, NotionRenderer } from "vue-notion";

export default {
  components: { NotionRenderer },
  data: () => ({ blockMap: null, blockTable:null }),
  async created() {
    // get Notion blocks from the API via a Notion pageId
    this.blockMap = await getPageBlocks("545fec43688d457c89d54d1b1a3ac5dd");
    this.blockTable = await getPageTable("10efc36b73004137bd635de3f1fac257")
  },
};
</script>

<style>
@import "vue-notion/src/styles.css"; /* optional Notion-like styles */
</style>

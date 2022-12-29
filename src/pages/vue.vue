<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script>
import { getPageBlocks, NotionRenderer } from "vue-notion";

export default {
  components: { NotionRenderer },
  data: () => ({ blockMap: null, blockTable:null }),
  async created() {
    // get Notion blocks from the API via a Notion pageId
    this.blockMap = await getPageBlocks("545fec43688d457c89d54d1b1a3ac5dd");
  },
};
</script>

<style>
@import "vue-notion/src/styles.css"; /* optional Notion-like styles */
</style>

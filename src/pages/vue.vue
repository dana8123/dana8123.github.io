<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script>
import { getPageBlocks, NotionRenderer } from "vue-notion";

export default {
  components: { NotionRenderer },
  data: () => ({ blockMap: null }),
  async created() {
    // get Notion blocks from the API via a Notion pageId
    this.blockMap = await getPageBlocks("37abeac23f8f445fb316884d3b8dbbcc");
  },
};
</script>

<style>
@import "vue-notion/src/styles.css"; /* optional Notion-like styles */
</style>

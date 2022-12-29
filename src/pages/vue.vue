<template>
  <div>
    <p><b>--Content from Notion should appear below--</b></p>
    <NotionRenderer v-if="headerMap" :blockMap="headerMap" />
    <p v-else>loading...</p>
    <p><b>--Content from Notion should appear above--</b></p>
  </div>
</template>

<script>
export default {
  data: () => ({ headerMap: null }),
  async fetch() {
    this.headerMap = await this.$notion.getPageBlocks(
      "03b76f42f2364d0897f0a0b8d8986795"
    );
  },
};
</script>
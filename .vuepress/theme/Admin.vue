<template>
  <div class="admin">
    后台管理
  </div>
</template>
<script>
import dayjs from "dayjs";
export default {
  computed: {
    author() {
      const { author } = this.$site.themeConfig;
      return author;
    },
    data() {
      return this.$page.frontmatter;
    },
  },
};
</script>

<style scoped>
.list {
  margin: 20px;
}
</style>

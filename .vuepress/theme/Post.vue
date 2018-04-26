<template>
  <div class="post">
    <el-row :gutter="12">
      <el-col :span="8">
        <el-card v-for="p in post" class="box-card list" key="p.path">
          <a :href="p.path">{{ p.title }}</a>
        </el-card>
      </el-col>
    </el-row>
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
    post() {
      let pages = this.$site.pages;
      let posts = [];
      pages.forEach(p => {
        if (p.frontmatter.type === "post") {
          p.frontmatter.date = dayjs(p.frontmatter.date).format("YYYY-MM-DD");
          posts.push(p);
        }
      });
      posts.sort(function(a, b) {
        return new Date(b.frontmatter.date) - new Date(a.frontmatter.date);
      });
      return posts;
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

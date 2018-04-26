<template>
  <div>
    <div v-if="data.post" class="content">
      <h1>{{data.title}}</h1>
    </div>
    <Content :custom="false" />
  </div>
</template>
<script>
export default {
  computed: {
    data() {
      return this.$page.frontmatter;
    },
  },
};
</script>

<style scoped>

</style>

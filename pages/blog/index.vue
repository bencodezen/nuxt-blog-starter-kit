<script>
export default {
  async asyncData({ $content }) {
    const postList = await $content('blog').fetch()
    const filteredResults = postList.map((item) => ({
      slug: item.slug,
    }))

    return {
      filteredResults,
    }
  },
}
</script>

<template>
  <div>
    <h1>Blog Page</h1>
    <p>{{ filteredResults }}</p>
  </div>
</template>

<style></style>

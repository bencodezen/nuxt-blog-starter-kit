<script>
export default {
  async asyncData({ $content, route }) {
    const post = await $content(route.path).fetch()

    return {
      post,
    }
  },
}
</script>

<template>
  <div>
    <h1>{{ post.title }}</h1>
    <nuxt-content :document="post" />
  </div>
</template>

<style></style>

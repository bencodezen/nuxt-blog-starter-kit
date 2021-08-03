<script>
export default {
  async asyncData({ $content }) {
    const postList = await $content('blog').fetch()

    return {
      postList,
    }
  },
}
</script>

<template>
  <div>
    <h1>Blog Page</h1>
    <ul>
      <li v-for="(post, index) in postList" :key="`post-${index}`">
        <h2>
          <nuxt-link :to="post.path"> {{ post.title }} </nuxt-link>
        </h2>
        <p v-if="post.description">{{ post.description }}</p>
        <nuxt-content v-else :document="{ body: post.excerpt }" />
      </li>
    </ul>
  </div>
</template>

<style></style>

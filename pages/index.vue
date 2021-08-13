<template>
  <div>
    <header>
      <nav>
        <nuxt-link to="/blog">Blog</nuxt-link>
      </nav>
      <p>Fetching Blog Data from Client Side Instead</p>
      <p>{{ clientBlogList }}</p>
    </header>
    <main>
      <h1>Home Page</h1>
    </main>
  </div>
</template>

<script>
export default {
  async created() {
    const clientBlogList = await fetch('/_content/blog').then((res) =>
      res.json()
    )

    return {
      clientBlogList,
    }
  },
}
</script>

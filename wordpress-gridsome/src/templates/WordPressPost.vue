
<template>
  <Layout :title="$page.post.title">
    <div v-html="$page.post.content"></div>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  post: wordPressPost (path: $path) {
    title
    content
  }
}
</page-query>

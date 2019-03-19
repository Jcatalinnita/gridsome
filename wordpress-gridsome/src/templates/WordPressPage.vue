
<template>
  <Layout :title="$page.page.title">
    <div v-html="$page.page.content"></div>
  </Layout>
</template>

<page-query>
query Page ($path: String!) {
  page: wordPressPage (path: $path) {
    title
    content
  }
}
</page-query>

<template>
  <Layout>
    <h1>{{$page.wordPressPage.title}}</h1>
    <div v-html="$page.wordPressPage.content"></div>
  </Layout>
</template>

<page-query>
query Page {
  wordPressPage(id: "2") {
    title,
    content
  }
}
</page-query>

export default {
<script> 
  metaInfo: {
    title: 'About us'
  }
</script>
}
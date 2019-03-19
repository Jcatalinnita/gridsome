
<template>
  <Layout :title="$page.post.title">
  
  	<div 
  		v-if="$page.post.featuredMedia"
  		class="image">
  		<img :src="$page.post.featuredMedia.sourceUrl" alt="" />
  	</div>
  	<h1>{{$page.post.title}}</h1>
    <div v-html="$page.post.content"></div>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  post: wordPressPost (path: $path) {
    title,
    content,
    featuredMedia {
      sourceUrl
    }
  }
}
</page-query>
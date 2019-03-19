
<template>
  <Layout 
  	:hero-background="$page.page.featuredMedia !== null ? $page.page.featuredMedia.sourceUrl : ''">

  	<template v-slot:hero>
	  	<div class="content"><h1>{{$page.page.title}}</h1></div>
  	</template>
    
    <div v-html="$page.page.content"></div>
  </Layout>
</template>

<page-query>
query Page ($path: String!) {
  page: wordPressPage (path: $path) {
    title,
    content,
    featuredMedia {
      sourceUrl
    }
  }
}
</page-query>

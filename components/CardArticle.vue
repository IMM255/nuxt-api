<template>
  <div class="col-md-4">
    <div class="row g-0 border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
      <div class=" article-img col-12 d-none d-lg-block">
        <img :src="article.image.small" alt="#">
      </div>
      <div class="col-12 p-4 d-flex flex-column position-static">
        <h4 class="mb-2">{{ article.title }}</h4>
        <p class="card-text mb-auto">{{article.contentSnippet}}</p>
        <a href="#" class="stretched-link">Continue reading</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'article'
  ]
}
</script>

<style>
  .article-img img{
    width: 100%;
  }
</style>

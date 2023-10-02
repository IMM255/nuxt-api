<template>
<div id="app">
  <TheHeader />
    <main class="container">
      <TheHero  />
      <div class="row mb-2">
        <CardArticle v-for="(article,index) in articles" :key="index" :article="article" />
      </div>
    </main>
</div>
</template>

<script>
import CardArticle from '../components/CardArticle.vue';
import TheHeader from '../components/TheHeader.vue';
import TheHero from '../components/TheHero.vue';

export default {
  components: { CardArticle,TheHeader,TheHero },
  data(){
    return {
        articles: []
    }
  },
  async fetch() {
    await this.$axios.$get('api/cnn-news')
      .then((res) => this.articles = res.data);
  },
  mounted(){
    console.log("Artikel: ",this.articles);
  }
}
</script>

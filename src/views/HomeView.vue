<template>
  <TopicSelect @get-topic="getTopicNews" />
  <main v-if="!loading" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
    <div v-for="(article, index) in articles" :key="index">
      <a :href="article.url" target="_blank">
        <DataTitle 
          :text="article.title" 
          :dataDate="article.publishedAt" 
          :imageUrl="article.urlToImage"
          :author="article.author"
          :description="article.description"
        />
      </a>
    </div>
  </main>
  <main v-else class="flex flex-col align-center justify-center text-center">
    <div class="text-gray-500 text-3xl mt-10 mb-6">
      Fetching Data
    </div>
    <img :src="require('../assets/hourglass.gif')" alt="" class="w-24 m-auto" />
  </main>
</template>

<script>
import DataTitle from '@/components/DataTitle.vue';
import TopicSelect from '@/components/TopicSelect.vue';

export default {
  name: "HomeView",
  components: {
    DataTitle,
    TopicSelect,
  },
  data() {
    return {
      loading: true,
      articles: '',
    }
  },
  methods: {
    async fetchNewsData() {
      const key = process.env.VUE_APP_API_KEY;
      const res = await fetch(
        `https://newsapi.org/v2/top-headlines?country=in&apiKey=${key}`
      );
      const data = await res.json();
      return data;
    },
    async getTopicNews(topic) {
      const key = process.env.VUE_APP_API_KEY;
      const res = await fetch(
        `https://newsapi.org/v2/top-headlines?country=in&category=${topic}&apiKey=${key}`
      );
      const data = await res.json();
      console.log("LOOOOOOOOOK HERE ", data);
      this.articles = data.articles;
    }
  },
  async created() {
    const data = await this.fetchNewsData();
    console.log(data);
    this.articles = data.articles;
    this.loading = false;
  },
};
</script>

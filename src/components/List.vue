<template>
  <div>
    <ListItem v-for="one in news" :key="one.id" :news="one"></ListItem>
  </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue';
import news from '@/news.json';

export default {
  data: () => ({
    news: []
  }),
  methods: {
    loadNews() {
      this.news = news;
    }
  },
  created() {
    this.loadNews();
  },
  components: {
    ListItem
  }
};
</script>

<style>
.app-card {
  margin-bottom: 20px;
}

.app-badge {
  user-select: none;
  cursor: pointer;
}
</style>

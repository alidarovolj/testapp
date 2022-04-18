<template>
  <div class="home">
    <div class="search">
      <div class="flex items-center mx-auto w-1/2 py-20 relative">
        <input v-model="query" @keyup="filterPhotos()" class="w-full p-3" type="text" placeholder="Поиск" />
        <i class="fa fa-magnifying-glass"></i>
      </div>
    </div>
    <div class="container mx-auto">
      <div class="my-10 flex flex-wrap w-full justify-between">
        <div class="w-1/5 p-2" v-for="item of allData.results" :key="item.id">
          <img @click="$router.push({name: 'single', params: { item: item }})" class="object-cover object-left h-full w-full" :src="item.urls.small" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HomeView",
  data() {
    return {
      url: "https://api.unsplash.com/search/photos/",
      client_id: "UxQcyiv7djwaIznmB6G73bYjldVCcICcUT4HZpscGcI",
      query: "",
      full_query: null,
      allData: {
        results: []
      },
    };
  },
  methods: {
    // https://api.unsplash.com/search/photos/?query={}&client_id=UxQcyiv7djwaIznmB6G73bYjldVCcICcUT4HZpscGcI
    async filterPhotos() {
      this.full_query = this.url + "?query={" + this.query + "}&client_id=" + this.client_id;
      const res = await axios.get(this.full_query);
      this.allData = res.data;
    }
  },
};
</script>

<template>
  <div class="home">
    <navbar />
    <div class="search">
      <div class="flex items-center mx-auto w-1/2 py-20 relative">
        <input class="w-full p-3" type="text" placeholder="Поиск">
        <i class="fa fa-magnifying-glass"></i>
      </div>
    </div>
    <div class="my-10 flex flex-wrap w-full justify-between">
      <div>
        
      </div>
    </div>
  </div>
</template>

<script>
import navbar from '../components/NavbarComp.vue'
export default {
  name: 'HomeView',
  components: {
    navbar
  }
}
</script>

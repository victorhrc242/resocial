<template>
  <div>
    <a v-for="banners in banners" :key="banners.id" :href="banners.link" target="_blank">
      <!-- Banner Desktop -->
      <img v-if="banners.imageUrl" class="banner desktop-banner" :src="banners.imageUrl" :alt="'Banner ' + banners.id">
      <!-- Banner Mobile -->
      <img v-if="banners.imageUrl" class="banner mobile-banner" :src="banners.imageUrl" :alt="'Banner ' + banners.id">
    </a>
  </div>
</template>

<script>
export default {
  name: "Banner",
  data() {
    return {
      banners: [],
    };
  },
  created() {
    this.loadBanners();
  },
  methods: {
    async loadBanners() {
      try {
        const response = await fetch('/public/db/db.json');
        const data = await response.json();
        this.banners = data.banners;  // Carrega todos os banners do db.json
      } catch (error) {
        console.error("Erro ao carregar banners:", error);
      }
    }
  }
};
</script>

<style scoped>
.banner {
  width: 1280px;
  height: 575px;
  display: block;
  margin: 0 auto;
  margin-left: -31px;
}

@media only screen and (min-width: 767px) {
  .mobile-banner {
    display: none;
  }
}

@media only screen and (max-width: 766px) {
  .desktop-banner {
    display: none;
  }
}
</style>

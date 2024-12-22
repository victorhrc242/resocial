<template>
  <div>
    <a v-for="banner in banners" :key="banner.id" :href="banner.link" target="_blank">
      <!-- Banner Desktop -->
      <img v-if="banner.imageUrl" class="banner desktop-banner" :src="banner.imageUrl" :alt="'Banner ' + banner.id">
      <!-- Banner Mobile -->
      <img v-if="banner.imageUrl" class="banner mobile-banner" :src="banner.imageUrl" :alt="'Banner ' + banner.id">
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
        const response = await fetch('/db/db.json');
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
  width: 100%;
  height: auto;
  display: block;
  margin: 0 auto;
}

@media only screen and (min-width: 767px) {
  .mobile-banner {
    display: none;
  }
  .desktop-banner {
    width: 1280px;
    height: 575px;
    margin-left: -31px; /* Ajuste para centralizar o banner */
  }
}

@media only screen and (max-width: 766px) {
  .desktop-banner {
    display: none;
  }
  .mobile-banner {
    width: 100%;
    height: auto;
  }
}
</style>

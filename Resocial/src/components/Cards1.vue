<template>
  <div class="cards-container">
    <div v-for="card in cards" :key="card.id" class="card">
      <img :src="card.imageUrl" :alt="card.title" class="card-image">
      <div class="card-content">
        <h3 class="card-title">{{ card.title }}</h3>
        <p class="card-description">{{ card.description }}</p>
        <a :href="card.link" target="_blank" class="card-link">Saiba mais</a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Cards1",
  data() {
    return {
      cards: []
    };
  },
  created() {
    this.loadCards();
  },
  methods: {
    async loadCards() {
      try {
        const response = await fetch('/db/db.json');
        const data = await response.json();
        this.cards = data.cards;  // Carrega os cards do db.json
      } catch (error) {
        console.error("Erro ao carregar os cards:", error);
      }
    }
  }
};
</script>
<style scoped>
.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-content {
  padding: 15px;
}

.card-title {
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.card-description {
  font-size: 1rem;
  margin-bottom: 15px;
  color: #555;
}

.card-link {
  text-decoration: none;
  color: #D4AF37;  /* Cor dourada */
  font-weight: bold;
}
</style>

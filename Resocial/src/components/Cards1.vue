<template>
  <div class="layout-container">
    <!-- Cards -->
    <div class="cards-container">
      <div v-for="card in cards" :key="card.id" class="card">
        <img :src="card.imageUrl" :alt="card.title" class="card-image">
        <div class="card-content">
          <h3 class="card-title">{{ card.title }}</h3>
          <p class="card-description">{{ card.description }}</p>
          <a :href="card.link" target="_blank" class="card-link">Ler Mais</a>
        </div>
      </div>
    </div>

    <!-- Publicidade -->
    <Publicidade />
  </div>
</template>

<script>
import Publicidade from './Publicidade.vue';
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
        const response = await fetch('/db/db.json'); // A URL é relativa e acessa o arquivo da pasta public
        const data = await response.json();
        this.cards = data.cards;  // Carrega os cards do db.json
      } catch (error) {
        console.error("Erro ao carregar os cards:", error);
      }
    }
  },
  components: {
    Publicidade,
  },
};
</script>

<style scoped>
/* Container principal para layout em linha */
.layout-container {
  display: flex;
  justify-content: space-between; /* Espaçamento entre os cards e a publicidade */
  align-items: flex-start; /* Alinha os itens ao topo */
  gap: 20px;
  padding: 20px;
  box-sizing: border-box;
}

/* Estilo dos cards */
.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); /* Responsivo */
  gap: 20px;
  flex: 2; /* Os cards ocupam mais espaço */
}

.card {
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
  color: #D4AF37; /* Cor dourada */
  font-weight: bold;
}

/* Responsividade para dispositivos menores */
@media only screen and (max-width: 768px) {
  .layout-container {
    flex-direction: column; /* Empilha cards e publicidade */
  }

  .cards-container {
    grid-template-columns: 1fr; /* Um card por linha */
  }
}
</style>

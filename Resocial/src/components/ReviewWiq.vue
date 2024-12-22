<template>
    <div class="layout-container">
      <!-- Carrossel -->
      <div class="carousel-container">
        <div class="carousel-card" v-for="(card, index) in visibleReviews" :key="card.id">
          <img :src="card.imageUrl" :alt="card.title" class="card-image">
          <div class="card-content">
            <h3 class="card-title">{{ card.title }}</h3>
            <p class="card-description">{{ card.description }}</p>
            <a :href="card.link" target="_blank" class="card-link">Ler Mais</a>
          </div>
        </div>
  
        <!-- Botões para navegação -->
        <button @click="prevSlide" class="carousel-btn prev-btn">←</button>
        <button @click="nextSlide" class="carousel-btn next-btn">→</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ReviewWiq",
    data() {
      return {
        reviews: [], // Inicia como um array vazio
        currentIndex: 0, // Controla o índice atual do carrossel
        visibleReviews: [] // Controla quais reviews são visíveis
      };
    },
    mounted() {
      // Simulação de requisição para obter os dados do db.json
      this.fetchReviews();
    },
    methods: {
      fetchReviews() {
        // Aqui simula-se a obtenção de dados de um arquivo local ou API
        fetch('db/db.json') // Substitua pelo caminho real
          .then(response => response.json())
          .then(data => {
            this.reviews = data.ReviewWiki; // Atualiza o estado com os dados
            this.updateVisibleReviews(); // Atualiza os reviews visíveis
          })
          .catch(error => console.error('Erro ao carregar os reviews:', error));
      },
      updateVisibleReviews() {
        const totalReviews = this.reviews.length;
        // Exibe 3 reviews por vez
        this.visibleReviews = [
          this.reviews[this.currentIndex % totalReviews],
          this.reviews[(this.currentIndex + 1) % totalReviews],
          this.reviews[(this.currentIndex + 2) % totalReviews]
        ];
      },
      nextSlide() {
        this.currentIndex = (this.currentIndex + 1) % this.reviews.length;
        this.updateVisibleReviews(); // Atualiza os reviews visíveis
      },
      prevSlide() {
        this.currentIndex = (this.currentIndex - 1 + this.reviews.length) % this.reviews.length;
        this.updateVisibleReviews(); // Atualiza os reviews visíveis
      }
    }
  };
  </script>
  
  <style scoped>
  .layout-container {
    padding: 20px;
  }
  
  .carousel-container {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .carousel-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #f5f5f5;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    width: 300px;
    height: 400px;
    margin: 0 10px;
    transition: transform 0.3s ease-in-out;
  }
  
  .card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
  }
  
  .card-content {
    padding: 15px;
    text-align: center;
  }
  
  .card-title {
    font-size: 18px;
    color: #333;
    margin-bottom: 10px;
  }
  
  .card-description {
    font-size: 14px;
    color: #666;
    margin-bottom: 15px;
  }
  
  .card-link {
    font-size: 14px;
    color: #0073e6;
    text-decoration: none;
  }
  
  .card-link:hover {
    text-decoration: underline;
  }
  
  /* Estilo dos botões de navegação */
  .carousel-btn {
    position: absolute;
    top: 50%;
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    font-size: 24px;
    padding: 10px;
    cursor: pointer;
    transform: translateY(-50%);
  }
  
  .prev-btn {
    left: 10px;
  }
  
  .next-btn {
    right: 10px;
  }
  
  .carousel-btn:hover {
    background-color: rgba(0, 0, 0, 0.7);
  }
  </style>
  
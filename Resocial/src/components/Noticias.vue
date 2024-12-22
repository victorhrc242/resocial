<template>
    <div class="layout-container">
      <!-- Cards -->
      <div class="cards-container">
        <div v-for="card in reviews" :key="card.id" class="card">
          <img :src="card.imageUrl" :alt="card.title" class="card-image">
          <div class="card-content">
            <h3 class="card-title">{{ card.title }}</h3>
            <p class="card-description">{{ card.description }}</p>
            <a :href="card.link" target="_blank" class="card-link">Ler Mais</a>
          </div>
        </div>
      </div>
    </div>
  </template>
  <script>
  export default {
    name: "Noticias",
    data() {
      return {
        reviews: [] // Inicia como um array vazio
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
            this.reviews = data.Reviws; // Atualiza o estado com os dados
          })
          .catch(error => console.error('Erro ao carregar os reviews:', error));
      }
    }
  };
  </script>
  
  <style scoped>.layout-container {
    padding: 20px;
  }
  
  .cards-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }
  
  /* Card */
  .card {
    background-color: #f5f5f5;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }
  
  .card-image {
    width: 100%;
    height: auto;
  }
  
  .card-content {
    padding: 15px;
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
  
  /* Media Queries para responsividade */
  @media (max-width: 768px) {
    .cards-container {
      grid-template-columns: repeat(2, 1fr); /* Duas colunas em telas menores */
    }
  
    .card-title {
      font-size: 16px; /* Ajusta o tamanho do título */
    }
  
    .card-description {
      font-size: 12px; /* Ajusta o tamanho da descrição */
    }
  
    .card-link {
      font-size: 12px; /* Ajusta o tamanho do link */
    }
  }
  
  @media (max-width: 480px) {
    .cards-container {
      grid-template-columns: 1fr; /* Uma coluna em telas muito pequenas */
    }
  
    .card-title {
      font-size: 14px; /* Ajusta o tamanho do título para telas pequenas */
    }
  
    .card-description {
      font-size: 10px; /* Ajusta o tamanho da descrição */
    }
  
    .card-link {
      font-size: 10px; /* Ajusta o tamanho do link */
    }
  }
  
  </style>
  
<template>
    <div class="Analizas">
      <div v-for="analise in analises" :key="analise.id" class="analise-item">
        <a :href="analise.link" class="imagem-container">
          <img :src="analise.imagemUrl" :alt="'Imagem de ' + analise.id" class="imagem" />
          <div class="overlay"></div>
        </a>
        <div class="Nota">{{ analise.nota }}</div>
        <div class="Texto">{{ analise.texto }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "Analises",
    data() {
      return {
        analises: [] // Aqui vamos armazenar todas as análises
      };
    },
    created() {
      // Carregar os dados do db.json
      this.carregarAnalises();
    },
    methods: {
      async carregarAnalises() {
        try {
          const resposta = await fetch("/db/db.json");
          const dados = await resposta.json();
          this.analises = dados.analises; // Carregar todas as análises para a página
        } catch (erro) {
          console.error("Erro ao carregar dados:", erro);
        }
      }
    }
  };
  </script>
  
  <style scoped>.Analizas {
    display: flex;
    flex-wrap: wrap; /* Permite que os itens se ajustem em várias linhas */
    gap: 20px; /* Espaço entre as análises */
    justify-content: center; /* Alinha as análises no centro */
  }
  
  .analise-item {
    position: relative;
    width: calc(33.333% - 20px); /* Cada item ocupa 1/3 da largura, com espaçamento */
    max-width: 500px; /* Limita a largura máxima do item */
    box-sizing: border-box;
    overflow: hidden; /* Garante que o overlay fique dentro do limite da imagem */
  }
  
  .imagem-container {
    position: relative;
    display: block; /* Faz o link envolver toda a área da imagem */
  }
  
  .imagem {
    width: 100%;
    height: auto;
    transition: opacity 0.3s ease; /* Transição suave na mudança de opacidade */
  }
  
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5); /* Fundo preto com opacidade */
    opacity: 0;
    transition: opacity 0.3s ease; /* Transição suave no efeito de hover */
  }
  
  .analise-item:hover .overlay {
    opacity: 1; /* Mostra o overlay ao passar o mouse */
  }
  
  .Nota {
    position: absolute;
    top: 10px;
    left: 10px;
    background-color: rgba(0, 0, 0, 0.5);
    color: #fff;
    padding: 5px 10px;
    border-radius: 5px;
    font-size: 16px;
  }
  
  .Texto {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: #fff;
    font-size: 18px;
    text-align: center;
  }
  
  /* Media Queries para responsividade */
  
  /* Para telas menores que 768px (como tablets) */
  @media (max-width: 768px) {
    .analise-item {
      width: calc(50% - 20px); /* Cada item ocupa metade da largura */
    }
  
    .Nota {
      font-size: 14px; /* Ajusta o tamanho da nota */
    }
  
    .Texto {
      font-size: 16px; /* Ajusta o tamanho do texto */
    }
  }
  
  /* Para telas menores que 480px (como smartphones) */
  @media (max-width: 480px) {
    .analise-item {
      width: 100%; /* Cada item ocupa a largura total */
    }
  
    .Nota {
      font-size: 12px; /* Ajusta o tamanho da nota */
    }
  
    .Texto {
      font-size: 14px; /* Ajusta o tamanho do texto */
    }
  }
  
  </style>
  
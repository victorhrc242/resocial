<template>
    <div>
      <footer>
        <div>
          <h1>Resocial</h1>
        </div>
      
        <ul class="lista-horizontal">
          <li><router-link to="/">Contato/</router-link></li>
          <li><router-link to="/">Parceiros/</router-link></li>
          <li><router-link to="/">Discord/</router-link></li>
          <li><router-link to="/">Se torne um Parceiro/</router-link></li>
        </ul>
  
        <div class="Baner-discord">
          <a href="https://discord.com" target="_blank">
            <i class="fab fa-discord"></i>Discord
          </a>
        </div>
  
        <h3>equipe Victorhugorodriguescosta242@gmail.com <i class="fas fa-postcard"></i></h3>
  
        <div class="Botão-para-voltar-ao-inicio">
          <button @click="scrollToTop">
            <i class="fas fa-arrow-up"></i> Voltar ao Início
          </button>
        </div>
      </footer>
    </div>
  </template>
  
  <script>
  export default {
    name: "Rodape",
    methods: {
      scrollToTop() {
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    }
  };
  </script>
  
  <style scoped>
  footer {
    background-color: #333;
    color: white;
    padding: 20px;
    text-align: center;
    font-family: Arial, sans-serif;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
  }
  
  ul li {
    margin: 0 15px;
  }
  
  .Baner-discord {
    background-color: transparent;
    color: white;
    padding: 10px;
    margin-top: 20px;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .Baner-discord a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    display: flex;
    align-items: center;
  }
  
  .Baner-discord a i {
    margin-right: 10px;
    font-size: 24px;
  }
  
  .Baner-discord a:hover {
    text-decoration: underline;
  }
  
  /* Centralizar o botão "Voltar ao Início" dentro da página */
  .Botão-para-voltar-ao-inicio {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 50px; /* Ajuste para posição desejada */
  }
  
  .Botão-para-voltar-ao-inicio button {
    background-color: #D4AF37;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    display: flex;
    align-items: center;
  }
  
  .Botão-para-voltar-ao-inicio button i {
    margin-right: 10px;
    font-size: 18px;
  }
  
  .Botão-para-voltar-ao-inicio button:hover {
    background-color: #B88A2D;
  }
  </style>
  
  <!-- Incluindo o CDN do Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
  
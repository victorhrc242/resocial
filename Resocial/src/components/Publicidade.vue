<template>
    <div class="sidebar-container">
      <div class="social-icons">
        <a href="https://www.facebook.com/seu-usuario" target="_blank" class="social-icon">
          <i class="fab fa-facebook"></i>
        </a>
        <a href="https://twitter.com/seu-usuario" target="_blank" class="social-icon">
          <i class="fab fa-twitter"></i>
        </a>
        <a href="https://www.instagram.com/seu-usuario" target="_blank" class="social-icon">
          <i class="fab fa-instagram"></i>
        </a>
        <a href="https://www.linkedin.com/in/seu-usuario" target="_blank" class="social-icon">
          <i class="fab fa-linkedin"></i>
        </a>
      </div>
  
      <div class="discord">
        <iframe src="https://discord.com/widget?id=seu-id-do-servidor&theme=dark" width="100%" height="500" allowtransparency="true" frameborder="0"></iframe>
      </div>
  
      <div class="publicidade">
        <h2>Publicidade</h2>
        <img src="https://ucb2.catolica.edu.br/portal/wp-content/uploads/2019/02/BANNER_UCB_WHITE_01-802x380px.png" alt="Publicidade 1" style="height: 235px; width: 305px;" class="publicidade-img">
        <h2>Publicidade</h2>
        <img src="https://grandesnomesdapropaganda.com.br/wp-content/uploads/2020/11/Godiva-Propaganda.jpg" alt="Publicidade 2" style="height: 235px; width: 305px;" class="publicidade-img">
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "Publicidade",
  };
  </script>
  
  <style scoped>
  /* Container principal */
  .sidebar-container {
    display: flex;
    flex-direction: column;
    width: 350px; /* Largura da barra lateral */
    height: auto; /* A altura agora se ajusta ao conteúdo */
    box-shadow: -2px 0 5px rgba(0, 0, 0, 0.1); /* Sombra para destaque */
    padding: 20px;
    box-sizing: border-box;
  }
  
  /* Estilo dos ícones sociais */
  .social-icons {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
  }
  
  .social-icon {
    font-size: 24px;
    color: #333;
    text-decoration: none;
  }
  
  .social-icon:hover {
    color: #0073e6;
  }
  
  /* Estilo do iframe do Discord */
  .discord iframe {
    width: 100%; /* Garante que o iframe ocupe toda a largura disponível */
    border-radius: 5px;
  }
  
  /* Estilo da seção de publicidade */
  .publicidade {
    margin-top: 20px;
  }
  
  .publicidade h2 {
    margin-bottom: 10px;
    font-size: 18px;
    color: #ffffff;
    text-align: center;
  }
  
  .publicidade-img {
    display: block;
    width: 100%; /* Garante que as imagens respeitem a largura do container */
    height: auto; /* Mantém a proporção das imagens */
    margin-bottom: 10px;
    border-radius: 5px;
  }
  </style>
  
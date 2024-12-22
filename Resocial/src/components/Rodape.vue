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
  width: 100%; /* Garante que o rodapé ocupe a largura total */
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
  font-family: Arial, sans-serif;
  box-sizing: border-box; /* Garante que o padding não altere a largura total */
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap; /* Permite que os itens se ajustem em várias linhas */
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

/* Media Queries para responsividade */

/* Para telas menores que 768px (como tablets) */
@media (max-width: 768px) {
  .Botão-para-voltar-ao-inicio button {
    font-size: 14px; /* Ajusta o tamanho da fonte */
    padding: 8px 16px; /* Ajusta o padding */
  }

  ul {
    flex-direction: column; /* Itens da lista se empilham em uma coluna */
    align-items: center; /* Centraliza os itens */
  }

  ul li {
    margin: 10px 0; /* Ajusta o espaçamento vertical */
  }

  .Baner-discord {
    margin-top: 20px; /* Ajusta o espaçamento superior */
  }
}

/* Para telas menores que 480px (como smartphones) */
@media (max-width: 480px) {
  footer {
    padding: 10px; /* Ajusta o padding para telas menores */
  }

  .Botão-para-voltar-ao-inicio button {
    font-size: 12px; /* Ajusta ainda mais o tamanho da fonte */
    padding: 6px 12px; /* Ajusta o padding */
  }

  ul {
    flex-direction: column; /* Empilha os itens em uma coluna */
    align-items: center; /* Centraliza os itens */
  }

  .Baner-discord {
    font-size: 14px; /* Ajusta o tamanho da fonte do banner */
    margin-top: 15px; /* Ajusta o espaçamento superior */
  }

  .Nota {
    font-size: 12px; /* Ajusta o tamanho da nota */
  }

  /* Evita que o rodapé se sobreponha ao conteúdo */
  .lista-horizontal {
    width: 100%; /* Garante que a lista ocupe toda a largura */
    padding: 0 10px; /* Ajusta a margem interna */
    box-sizing: border-box;
  }
}
</style>

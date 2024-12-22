<template>
  <div class="Navbar">
    <nav>
      <ul>
        <!-- Usando router-link em vez de a -->
        <li><router-link to="/">Início</router-link></li>
        <li><router-link to="#noticias">Notícias</router-link></li>
        <li class="dropdown">
          <a href="javascript:void(0)" class="dropbtn">Jogos</a>
          <div class="dropdown-content">
            <router-link to="#re1">Resident Evil 1</router-link>
            <router-link to="#re2">Resident Evil 2 Remake</router-link>
            <router-link to="#village">Resident Evil Village</router-link>
          </div>
        </li>
        <li class="dropdown">
          <a href="javascript:void(0)" class="dropbtn">Filmes</a>
          <div class="dropdown-content">
            <router-link to="#filmes-clas">Filmes Clássicos</router-link>
            <router-link to="#series">Séries</router-link>
          </div>
        </li>
        <li><router-link to="#contato">Contato</router-link></li>
      </ul>
    </nav>
  </div>
  <RouterView/>
</template>
<script>
export default {
  name: "Navbar",
};
</script>
<style scoped>
/* Estilo geral da barra de navegação */
nav {
  position: fixed; /* Fixa o menu no topo da página */
  top: 0; /* Alinha o menu ao topo */
  left: 0; /* Inicia no canto esquerdo */
  width: 100%; /* Faz o menu ocupar toda a largura da página */
  background-color: #38444d; /* Fundo do menu */
  z-index: 1000; /* Garante que o menu fique sobre outros elementos */
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.3); /* Sombra para destaque */
}
ul {
  list-style-type: none;
  margin: 0;
  padding: 10px;
  overflow: hidden;
  display: flex;
  justify-content: flex-end;
}
li {
  display: inline-block;
  padding: 0 10px;
}
/* Estilo aplicado ao router-link para garantir que se comporte como um link */
router-link {
  display: block;
  color: white;
  text-align: left;
  padding: 14px 16px;
  text-decoration: none;
}
/* Hover para router-link */
router-link:hover {
  background-color: red;
}
li.dropdown {
  display: inline-block;
}
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
}
.dropdown-content router-link {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}
/* Hover para links dentro do dropdown */
.dropdown-content router-link:hover {
  background-color: #f1f1f1;
}
.dropdown:hover .dropdown-content {
  display: block;
}
body {
  margin: 50px 0 0 0;
  background-color: white;
}
</style>

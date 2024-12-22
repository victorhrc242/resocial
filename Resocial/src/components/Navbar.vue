<template>
  <div class="Navbar">
    <nav>
      <div class="menu-toggle" @click="toggleMenu">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
      <ul :class="{'active': menuActive}">
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
  data() {
    return {
      menuActive: false, // Controla a visibilidade do menu
    };
  },
  methods: {
    toggleMenu() {
      this.menuActive = !this.menuActive; // Alterna a visibilidade do menu
    }
  }
};
</script>

<style scoped>
/* Estilo geral da barra de navegação */
nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #38444d;
  z-index: 1000;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.3);
  padding: 10px;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: flex-end;
  flex-wrap: wrap;
}

li {
  display: inline-block;
  padding: 0 10px;
}

router-link {
  display: block;
  color: white;
  text-align: left;
  padding: 14px 16px;
  text-decoration: none;
}

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

/* Responsividade */
@media screen and (max-width: 768px) {
  /* Esconde o menu e mostra o ícone de três risquinhos */
  .menu-toggle {
    display: block;
    cursor: pointer;
  }

  .menu-toggle .bar {
    display: block;
    width: 30px;
    height: 5px;
    margin: 6px auto;
    background-color: white;
  }

  ul {
    display: none;
    flex-direction: column;
    width: 100%;
    align-items: flex-start;
  }

  ul.active {
    display: flex; /* Exibe o menu quando ativo */
  }

  li {
    width: 100%;
    text-align: center;
  }

  .dropdown-content {
    position: static;
    box-shadow: none;
  }

  .dropdown:hover .dropdown-content {
    display: none;
  }
}
</style>

<template>
  <header :class="{ 'scrolled': scrolled }">
    <nav>
      <div class="logo">
        <img src="../img/logo.png" alt="Logo de José Ginés">
      </div>
      <ul>
        <li><a href="#inicio" @click.prevent="scrollToSection('inicio')">Inicio</a></li>
        <li><a href="#acerca-de" @click.prevent="scrollToSection('acerca-de')">Acerca de mí</a></li>
        <li><a href="#conocimientos" @click.prevent="scrollToSection('conocimientos')">Conocimientos</a></li>
        <li><a href="#proyectos" @click.prevent="scrollToSection('proyectos')">Proyectos</a></li>
        <li><a href="#contacto" @click.prevent="scrollToSection('contacto')">Contacto</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderSection',
  data() {
    return {
      scrolled: false
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 50;
    },
    scrollToSection(id) {
      const targetElement = document.querySelector(`#${id}`);
      if (targetElement) {
        // Altura de tu header (aproximadamente 100px, podrías obtenerla dinámicamente si es variable)
        const headerHeight = 100; // Ajusta este valor si tu header tiene una altura diferente

        // Calcula la posición a la que debería desplazarse la ventana
        // Resta la altura del header para que el elemento quede visible justo debajo de él
        const offsetTop = targetElement.getBoundingClientRect().top + window.pageYOffset - headerHeight;

        window.scrollTo({
          top: offsetTop,
          behavior: 'smooth'
        });
      }
    }
  }
};
</script>

<style scoped>
/* Los estilos scoped deben estar aquí */
header {
    background-color: var(--dark-bg);
    padding: var(--spacing) 0;
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    z-index: 1000;
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--spacing);
}

nav .logo img {
    height: 40px;
    vertical-align: middle;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

nav ul li {
    margin-left: 30px;
}

nav ul li a {
    color: var(--light-text);
    font-weight: bold;
    font-size: 1.1em;
    padding: 5px 0;
    position: relative;
}

nav ul li a::after {
    content: '';
    position: absolute;
    width: 0;
    height: 2px;
    background-color: var(--primary-color);
    left: 0;
    bottom: -5px;
    transition: width 0.3s ease-in-out;
}

nav ul li a:hover::after {
    width: 100%;
}
</style>
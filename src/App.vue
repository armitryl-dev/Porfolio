<template>
  <div id="app">
    <Header />
    <main>
      <Hero />
      <About />
      <Knowledge />
      <Projects />
      <Contact />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './assets/components/Header.vue';
import Hero from './assets/components/Hero.vue';
import About from './assets/components/About.vue';
import Knowledge from './assets/components/Knowledge.vue';
import Projects from './assets/components/Projects.vue';
import Contact from './assets/components/Contact.vue';
import Footer from './assets/components/Footer.vue';

import 'highlight.js/styles/atom-one-dark.min.css'; // Importa Highlight.js CSS globalmente

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    About,
    Knowledge,
    Projects,
    Contact,
    Footer
  },
  mounted() {
    // Importar Highlight.js dinámicamente si es necesario, o depender de la configuración global
    // Para un enfoque más limpio, podrías inicializar highlight.js en los componentes donde se utiliza
  }
};
</script>

<style>
/* Importar estilos globales de style.css */
@import './assets/styles/style.css';
</style>
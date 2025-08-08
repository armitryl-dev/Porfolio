<template>
  <footer>
    <p>&copy; 2025 José Ginés. Todos los derechos reservados.</p>
    <p>Porfolio desarrollado usando VueJs 3.5.18</p>
  </footer>
</template>

<script>
export default {
  name: 'FooterSection'
};
</script>

<style scoped>
/* Estilos específicos del Footer de style.css */
footer {
    background-color: var(--dark-bg);
    color: var(--secondary-color);
    padding: var(--spacing) 0;
    text-align: center;
    font-size: 0.9em;
    border-top: 1px solid rgba(255,255,255,0.1);
}
</style>
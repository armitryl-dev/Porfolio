<template>
  <section id="contacto" class="contact">
    <div class="container">
      <h2>Contacto</h2>
      <p>No dudes en contactarme para cualquier consulta.</p>
      
      <p class="contact-email-text">joseginesmartineznicolas@gmail.com</p>

      <div class="contact-links">
        <a href="mailto:joseginesmartineznicolas@gmail.com" target="_blank" aria-label="Enviar Email">
          <img src="../img/email.png" alt="Email" class="contact-icon">
        </a>
        <a href="https://www.linkedin.com/in/joseginesmartinez99" target="_blank" aria-label="LinkedIn">
          <img src="../img/linkedin.png" alt="LinkedIn" class="contact-icon">
        </a>
        <a href="https://github.com/armitryl-dev" target="_blank" aria-label="GitHub">
          <img src="../img/github.png" alt="GitHub" class="contact-icon">
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactSection'
};
</script>

<style scoped>
/* Estilos específicos de la sección Contact */
.contact-links {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: var(--spacing);
    margin-top: 30px;
}

.contact-icon {
    width: 50px;
    height: 50px;
    transition: transform 0.2s ease-in-out;
}

.contact-links a:hover .contact-icon {
    transform: scale(1.1);
}

/* Estilo para el email de texto */
.contact-email-text {
    font-size: 1.1em;
    font-weight: bold;
    margin-top: var(--spacing);
    color: var(--primary-color);
}

@media (max-width: 768px) {
    .contact-icon {
        width: 40px;
        height: 40px;
    }
}
</style>
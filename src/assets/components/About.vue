<template>
  <section id="acerca-de" class="about">
    <div class="container">
      <h2>Acerca de mí</h2>
      <p>Soy un desarrollador recién titulado con un Grado Superior en Desarrollo de Aplicaciones Multiplataforma, con conocimientos tanto en desarrollo web como móvil. 
        Mi mayor motivación es encontrar soluciones eficientes a desafíos técnicos y mi pasión por el aprendizaje continuo me impulsa a crecer profesionalmente.
        Estoy buscando una oportunidad laboral donde pueda aportar valor a un equipo, aplicar mis conocimientos técnicos y, a la vez, seguir ampliando mis horizontes 
        profesionales con nuevas tecnologías y metodologías.</p>
      <p>Fuera del código, disfruto de mis amigos, de vez en cuando los videojuegos, la lectura, la música, aunque mi pasión son los coches y sobre todo, el boxeo.</p>
      <a :href="cvPath" download="CV_Jose_Gines.pdf" class="btn btn-primary-cv">Descargar CV</a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutSection',
  computed: {
    cvPath() {
      return `${import.meta.env.BASE_URL}/assets/pdf/CV.pdf`;
    }
  }
};
</script>

<style scoped>
/* Estilos específicos de la sección About de style.css */
.about .container {
    text-align: left;
    max-width: 800px;
}

.about p {
    font-size: 1.1em;
    margin-bottom: var(--spacing);
}

/* Estilos generales de los botones para .btn y .btn-primary-cv */
.btn {
    display: inline-block;
    background-color: var(--primary-color);
    color: var(--light-text);
    padding: 12px 25px;
    border-radius: 5px;
    text-transform: uppercase;
    font-weight: bold;
    transition: background-color 0.3s ease, transform 0.2s ease;
    text-align: center;
    margin-top: 10px;
}

.btn:hover {
    background-color: #0056b3;
    transform: translateY(-2px);
}
</style>
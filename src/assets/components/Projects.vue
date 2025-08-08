<template>
  <section id="proyectos" class="projects">
    <div class="container">
      <h2>Mis Proyectos</h2>
      <div class="projects-grid">
        <div class="project-card">
          <img src="../img/umbralis.jpg" alt="Logo de Umbralis RPG" class="project-logo">
          <h3>Umbralis: RPG por Turnos</h3>
          <p>Juego RPG por turnos desarrollado en Kotlin y Jetpack Compose para Android nativo. El proyecto se encuentra en activo desarrollo, con planes de ser publicado en Google Play Store.</p>
          <div class="project-links">
            <a href="https://appdistribution.firebase.dev/i/fb0b1b28bfb29a23" target="_blank" class="btn-small">Instalar demo</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectsSection'
};
</script>

<style scoped>
/* Estilos específicos de la sección Projects de style.css */
.projects-grid {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    gap: var(--spacing);
    margin-top: 40px;
    flex-wrap: wrap;
}

.project-card {
    background-color: var(--card-bg);
    padding: var(--spacing);
    border-radius: 16px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.3);
    text-align: left;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    max-width: 350px;
    width: 100%;
}

.project-card .project-logo {
    width: 150px;
    height: 150px;
    object-fit: contain;
    margin: 0 auto 15px auto;
    border-radius: 50%;
    box-shadow: 0 2px 5px rgba(0,0,0,0.3);
    padding: 5px;
}

.project-card h3 {
    color: var(--primary-color);
    margin-top: 0;
    text-align: center;
}

.project-card p {
    font-size: 0.95em;
    margin-bottom: 20px;
    flex-grow: 1;
    text-align: center;
}

.project-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    justify-content: center;
}

.project-links .btn-small {
    flex-grow: 1;
    text-align: center;
}

.btn-small {
    padding: 8px 15px;
    font-size: 0.9em;
}

/* Estilos generales de los botones para .btn */
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

.project-link-icon {
    width: 50px;
    height: 50px;
    transition: transform 0.2s ease-in-out;
    margin-top: 30px;
}

a:hover .project-link-icon {
    transform: scale(1.1);
}

@media (max-width: 768px) {
    .projects-grid {
        max-width: 350px;
        margin-left: auto;
        margin-right: auto;
    }

    .project-card {
        padding: 15px;
    }
}
</style>
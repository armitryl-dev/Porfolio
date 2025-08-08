<template>
  <section id="inicio" class="hero">
    <div class="hero-content">
      <h1><span id="typing-text">{{ typedText }}</span><span class="blinking-cursor">|</span></h1>
      <p>Desarrollador multiplataforma apasionado por crear soluciones innovadoras, con un enfoque en la usabilidad y rendimiento.</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
  data() {
    return {
      textToType: "Hola, soy José Ginés",
      typedText: "",
      charIndex: 0,
      typingSpeed: 100,
      deletingSpeed: 50,
      delayBetweenCycles: 2000
    };
  },
  mounted() {
    this.typeText();
  },
  methods: {
    typeText() {
      if (this.charIndex < this.textToType.length) {
        this.typedText += this.textToType.charAt(this.charIndex);
        this.charIndex++;
        setTimeout(this.typeText, this.typingSpeed);
      } else {
        setTimeout(this.deleteText, this.delayBetweenCycles);
      }
    },
    deleteText() {
      if (this.charIndex > 0) {
        this.typedText = this.textToType.substring(0, this.charIndex - 1);
        this.charIndex--;
        setTimeout(this.deleteText, this.deletingSpeed);
      } else {
        setTimeout(this.typeText, this.delayBetweenCycles);
      }
    }
  }
};
</script>

<style scoped>
/* Estilos específicos de la sección Hero de style.css */
.hero {
    background: url('/assets/img/background.jpg') no-repeat center center/cover; /* Reemplaza con tu ruta real de imagen de fondo */
    height: 70vh;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--light-text);
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    position: relative;
    overflow: hidden;
}

.hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
    z-index: 1;
}

.hero-content {
    z-index: 2;
    max-width: 800px;
}

.hero-content h1 {
    font-size: 3.5em;
    margin-bottom: 10px;
    color: var(--light-text);
}

.hero-content p {
    font-size: 1.5em;
    margin-bottom: 30px;
}

/* Estilos específicos del efecto de escritura */
.blinking-cursor {
    font-weight: 100;
    font-size: 1.2em;
    color: var(--primary-color);
    animation: 0.8s ease-in-out infinite alternate blink-caret;
}

@keyframes blink-caret {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

@media (max-width: 768px) {
    .hero-content h1 {
        font-size: 2.5em;
    }

    .hero-content p {
        font-size: 1.2em;
    }
}

@media (max-width: 480px) {
    .hero-content h1 {
        font-size: 2em;
    }

    .hero-content p {
        font-size: 1em;
    }
}
</style>
<template>
  <section id="conocimientos" class="knowledge">
    <div class="container">
      <h2>Conocimientos</h2>
      <div id="code-knowledge-container" class="code-block">
        <pre><code class="language-javascript" ref="knowledgeCodeContent"></code></pre>
      </div>
    </div>
  </section>
</template>

<script>
import hljs from 'highlight.js/lib/core';
import javascript from 'highlight.js/lib/languages/javascript';

hljs.registerLanguage('javascript', javascript);

export default {
  name: 'KnowledgeSection',
  data() {
    return {
      myKnowledge: {
        languages: ["Java", "Kotlin", "JavaScript", "TypeScript", "Python", "HTML5", "CSS3"],
        frameworksLibraries: ["React.js", "Vue.js", "Jetpack Compose", "React Native", "Django"],
        databases: ["MongoDB", "Firebase Firestore", "MySQL", "PostgreSQL", "MariaDB", "Hibernate"],
        tools: ["Git & GitHub", "Docker", "Apache2", "Firebase Auth", "Capacitor", "Figma"]
      }
    };
  },
  mounted() {
    this.generateKnowledgeCode();
    hljs.highlightElement(this.$refs.knowledgeCodeContent); // Resaltar el bloque de código
  },
  methods: {
    generateKnowledgeCode() {
      let codeString = `const myKnowledge = {\n`;

      codeString += `    languages: [\n`;
      this.myKnowledge.languages.forEach(lang => {
        codeString += `        "${lang}",\n`;
      });
      codeString = codeString.slice(0, -2) + "\n";
      codeString += `    ],\n`;

      codeString += `    frameworksLibraries: [\n`;
      this.myKnowledge.frameworksLibraries.forEach(fw => {
        codeString += `        "${fw}",\n`;
      });
      codeString = codeString.slice(0, -2) + "\n";
      codeString += `    ],\n`;

      codeString += `    databases: [\n`;
      this.myKnowledge.databases.forEach(db => {
        codeString += `        "${db}",\n`;
      });
      codeString = codeString.slice(0, -2) + "\n";
      codeString += `    ],\n`;

      codeString += `    tools: [\n`;
      this.myKnowledge.tools.forEach(tool => {
        codeString += `        "${tool}",\n`;
      });
      codeString = codeString.slice(0, -2) + "\n";
      codeString += `    ]\n`;

      codeString += `};`;

      this.$refs.knowledgeCodeContent.textContent = codeString;
    }
  }
};
</script>

<style scoped>
/* Estilos específicos de la sección Skills de style.css */
.code-block {
    background-color: #2d2d2d;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.5);
    margin: 40px auto;
    padding: 0;
    max-width: 700px;
    text-align: left;
    overflow-x: auto;
}

.code-block pre,
.code-block pre code {
    margin: 0;
    padding: 25px;
    background-color: #1a1a1a;
    color: #f0f0f0;
    font-family: 'JetBrains Mono', 'Fira Code', 'JetBrains Mono', 'Consolas', 'Monaco', monospace;
    font-size: 0.95em;
    display: block;
    white-space: pre-wrap;
}
</style>
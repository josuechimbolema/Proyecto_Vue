<template>
  <section class="hero">
    <div class="content">
      <h1>Tu equipamiento de fútbol favorito </h1>
      <p>
        Camisetas, pantalonetas, busos, medias y zapatos de las mejores marcas.
        ¡Todo lo que necesitas para jugar como un profesional!
      </p>
      <a href="#productos" class="boton">Ver Productos</a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Hero'
}
</script>

<style scoped>
.hero {
  background-color: #16213e;
  min-height: 80vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 3rem;
}

.content {
  max-width: 700px;
}

h1 {
  color: #ffffff;
  font-size: 2rem;
  margin-bottom: 1rem;
}

p {
  color: #cccccc;
  font-size: 1rem;
  margin-bottom: 2rem;
  line-height: 1;
}

.boton {
  background-color: #00d4aa;
  color: #1a1a2e;
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
  font-size: 1.1rem;
  display: inline-block;
  transition: all 0.3s ease;
}

.boton:hover {
  background-color: #ffffff;
  box-shadow: 0 8px 20px rgba(0, 212, 170, 0.5);
  transform: scale(1.05);
}
</style>
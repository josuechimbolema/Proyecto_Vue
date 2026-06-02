<template>
  <footer class="footer">
    <div class="contenido">
      <h3>⚽ FutbolStore</h3>
      <p>Tu tienda de equipamiento deportivo de confianza</p>
      <div class="links">
        <a href="#productos">Productos</a>
        <a href="#contacto">Contacto</a>
      </div>
      <p class="copy">© 2026 FutbolStore. Todos los derechos reservados.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
.footer {
  background-color: #1a1a2e;
  padding: 3rem 2rem;
  text-align: center;
}

.contenido {
  max-width: 600px;
  margin: 0 auto;
}

h3 {
  color: #00d4aa;
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
}

p {
  color: #aaaaaa;
  margin-bottom: 1.5rem;
}

.links {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 1.5rem;
}

.links a {
  color: white;
  text-decoration: none;
  font-size: 1rem;
}

.links a:hover {
  color: #00d4aa;
  transition: color 0.3s;
}

.copy {
  color: #555555;
  font-size: 0.85rem;
}
</style>
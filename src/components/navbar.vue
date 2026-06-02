<template>
  <nav class="navbar">
    <h1 class="logo">⚽ FutbolStore</h1>
    <button class="hamburger" @click="menuAbierto = !menuAbierto">☰</button>
    <ul :class="['links', { abierto: menuAbierto }]">
      <li><a href="#productos" @click="menuAbierto = false">Productos</a></li>
      <li><a href="#contacto" @click="menuAbierto = false">Contacto</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return { menuAbierto: false }
  }
}
</script>

<style>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #1a1a2e;
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  z-index: 100;
  flex-wrap: wrap;
}

.logo {
  color: #00d4aa;
  font-size: 1.5rem;
  margin: 0;
}

.hamburger {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 1.8rem;
  cursor: pointer;
}

.links {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.links a {
  color: white;
  text-decoration: none;
  font-size: 2rem;
}

.links a:hover {
  color: #00d4aa;
}

@media (max-width: 600px)  {
  .hamburger {
    display: block;
  }

  .links {
    display: none;
    flex-direction: column;
    width: 100%;
    gap: 2rem;
    padding-top: 1rem;
  }

  .links.abierto {
    display: flex;
  }
}
</style>
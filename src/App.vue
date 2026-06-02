<template>
  <Navbar />
  <Hero />
  <Productos />
  <Formulario />
  <Footer />
</template>

<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Productos from './components/Productos.vue'
import Formulario from './components/Formulario.vue'
import Footer from './components/Footer.vue'

export default {
  components: {
    Navbar,
    Hero,
    Productos,
    Formulario,
    Footer
  }
}
</script>
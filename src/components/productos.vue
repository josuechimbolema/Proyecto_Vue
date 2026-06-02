<template>
  <section id="productos" class="productos">
    <h2>Nuestros Productos</h2>
    <div class="grid">
      <div v-for="producto in productos" :key="producto.id" class="card">
        <img :src="producto.imagen" :alt="producto.nombre" class="imagen" />
        <h3>{{ producto.nombre }}</h3>
        <p>{{ producto.descripcion }}</p>
        <span class="precio">{{ producto.precio }}</span>
        <button class="boton">Agregar al carrito</button>
      </div>
    </div>
  </section>
</template>

<script>
import camiseta from '../assets/camiseta.png'
import pantaloneta from '../assets/pantaloneta.png'
import buso from '../assets/buso.png'
import medias from '../assets/medias.png'
import zapatos from '../assets/zapatos.jpg'
import kit from '../assets/kit.png'

export default {
  name: 'Productos',
  data() {
    return {
      productos: [
        { id: 1, nombre: 'Camiseta Local', precio: '$25.00', imagen: camiseta, descripcion: 'Camiseta oficial de alta calidad' },
        { id: 2, nombre: 'Pantaloneta', precio: '$18.00', imagen: pantaloneta, descripcion: 'Cómoda y resistente para el juego' },
        { id: 3, nombre: 'Buso Deportivo', precio: '$35.00', imagen: buso, descripcion: 'Ideal para entrenamientos y frío' },
        { id: 4, nombre: 'Medias de Fútbol', precio: '$8.00', imagen: medias, descripcion: 'Pack de 3 pares antideslizantes' },
        { id: 5, nombre: 'Zapatos de Fútbol', precio: '$75.00', imagen: zapatos, descripcion: 'Tacos profesionales para césped' },
        { id: 6, nombre: 'Kit Completo', precio: '$130.00', imagen: kit, descripcion: 'Camiseta + pantaloneta + medias' },
      ]
    }
  }
}
</script>

<style scoped>
.productos {
  background-color: #0f3460;
  padding: 4rem 2rem;
}

h2 {
  color: #00d4aa;
  text-align: center;
  font-size: 2rem;
  margin-bottom: 2rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
  max-width: 1100px;
  margin: 0 auto;
}

.card {
  background-color: #16213e;
  border-radius: 12px;
  padding: 1.5rem;
  text-align: center;
  color: white;
  transition: transform 0.3s;
}

.card:hover {
  transform: scale(1.03);
  box-shadow: 0 8px 20px rgba(0, 212, 170, 0.3);
}

.imagen {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 1rem;
}

h3 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

p {
  font-size: 0.9rem;
  color: #aaaaaa;
  margin-bottom: 1rem;
}

.precio {
  font-size: 1.3rem;
  font-weight: bold;
  color: #00d4aa;
  display: block;
  margin-bottom: 1rem;
}

.boton {
  background-color: #00d4aa;
  color: #1a1a2e;
  border: none;
  padding: 0.6rem 1.2rem;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
  transition: opacity 0.3s;
}

.boton:hover {
  opacity: 0.85;
  transform: scale(1.05);
}
</style>
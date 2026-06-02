<template>
  <section id="contacto" class="formulario">
    <h2>Pedidos a Domicilio</h2>
    <p class="subtitulo"> Completa el formulario y te contactamos para coordinar tu envío</p>

    <div v-if="enviado" class="exito">¡Pedido recibido! Te contactaremos pronto </div>

    <div class="form-container">
      <div class="campo">
        <label>Nombre completo</label>
        <input v-model="form.nombre" type="text" placeholder="" />
        <p v-if="errores.nombre" class="error">⚠ {{ errores.nombre }}</p>
      </div>

      <div class="campo">
        <label>Correo electrónico</label>
        <input v-model="form.email" type="email" placeholder="" />
        <p v-if="errores.email" class="error">⚠ {{ errores.email }}</p>
      </div>

      <div class="campo">
        <label>Teléfono / WhatsApp</label>
        <input v-model="form.telefono" type="tel" placeholder="" />
        <p v-if="errores.telefono" class="error">⚠ {{ errores.telefono }}</p>
      </div>

      <div class="campo">
        <label>Dirección de entrega</label>
        <input v-model="form.direccion" type="text" placeholder="" />
        <p v-if="errores.direccion" class="error">⚠ {{ errores.direccion }}</p>
      </div>

      <div class="campo">
        <label>¿Qué productos deseas pedir?</label>
        <textarea v-model="form.mensaje" placeholder=""></textarea>
        <p v-if="errores.mensaje" class="error">⚠ {{ errores.mensaje }}</p>
      </div>

      <button class="boton" @click="enviar"> Realizar pedido</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Formulario',
  data() {
    return {
      form: { nombre: '', email: '', telefono: '', direccion: '', mensaje: '' },
      errores: {},
      enviado: false
    }
  },
  methods: {
    validar() {
      const errores = {}
      if (!this.form.nombre.trim()) errores.nombre = 'El nombre es obligatorio'
      if (!this.form.email.trim()) errores.email = 'El email es obligatorio'
      else if (!/\S+@\S+\.\S+/.test(this.form.email)) errores.email = 'Email no válido'
      if (!this.form.telefono.trim()) errores.telefono = 'El teléfono es obligatorio'
      else if (!/^\d{7,15}$/.test(this.form.telefono.replace(/\s/g, ''))) errores.telefono = 'Teléfono no válido'
      if (!this.form.direccion.trim()) errores.direccion = 'La dirección es obligatoria'
      else if (this.form.direccion.trim().length < 10) errores.direccion = 'Ingresa una dirección más completa'
      if (!this.form.mensaje.trim()) errores.mensaje = 'El mensaje es obligatorio'
      else if (this.form.mensaje.trim().length < 10) errores.mensaje = 'El mensaje debe tener al menos 10 caracteres'
      return errores
    },
    enviar() {
      this.errores = this.validar()
      if (Object.keys(this.errores).length === 0) {
        this.enviado = true
        this.form = { nombre: '', email: '', telefono: '', direccion: '', mensaje: '' }
      }
    }
  }
}
</script>

<style scoped>
.formulario {
  background-color: #16213e;
  padding: 4rem 2rem;
  text-align: center;
}

h2 {
  color: #00d4aa;
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.subtitulo {
  color: #aaaaaa;
  margin-bottom: 2rem;
}

.form-container {
  max-width: 500px;
  margin: 0 auto;
  text-align: left;
}

.campo {
  margin-bottom: 1.2rem;
}

label {
  color: white;
  display: block;
  margin-bottom: 0.4rem;
  font-size: 0.95rem;
}

input, textarea {
  width: 100%;
  padding: 0.8rem;
  border-radius: 8px;
  border: 1px solid #00d4aa;
  background-color: #0f3460;
  color: white;
  font-size: 1rem;
  box-sizing: border-box;
}

textarea {
  height: 120px;
  resize: none;
}

.error {
  color: #ff6b6b;
  font-size: 0.85rem;
  margin-top: 0.3rem;
}

.exito {
  color: #00d4aa;
  font-size: 1rem;
  margin-bottom: 1rem;
}

.boton {
  background-color: #00d4aa;
  color: #1a1a2e;
  border: none;
  padding: 0.8rem 2rem;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
  font-size: 1rem;
  width: 100%;
  margin-top: 0.5rem;
  transition: opacity 0.3s;
}

.boton:hover {
  opacity: 0.85;
}
</style>
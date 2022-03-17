<template>
  <div>
    <form action="name" @submit.prevent="contacto">
      <label for="">Nombre </label>
      <input type="text"
        v-model="name"
        id="name"
        required
        placeholder="ingresa tu nombre"
      >
      <br>
      <label for="emailasd">Email </label>
      <input type="email"
        v-model="email"
        id="email"
        required
        placeholder="ingresa tu e-mail"
      >
      <br>
      <label for="password">Contraseña </label>
      <input 
        type="password"
        v-model="editedpassword"
        id="password"
        required
        placeholder="ingresa tu contraseña"
      >
      <p v-if="editedpassword && !passwordHasNumbers">Error al menos la contraseña debe tener un numero</p>
      <br>
      <input type="submit" value="enviar"> 

    </form>
    
  </div>
</template>

<script>
export default {
  name: 'FormWeb',
  data(){
    return {
      name: '',
      email: '',
      editedpassword: false,
    }
  },
  computed: {
    passwordHasNumbers(){
      return /\d/.test(this.editedpassword);
    }
  }
}
</script>

<style>

</style>
<template>
  <div>
    <form @submit.prevent="enviarTareas">
      <div class="form-group">
        <label for="tarea">Ingresa una tarea</label>
        <input type="text" class="form-control" v-model="tarea">
        <small id="emailHelp" class="form-text text-muted">Escribe aquí</small>
      </div>
      <div class="form-group">
        <label for="imagen">Ingresa una imagen</label>
        <input type="text" class="form-control" v-model="imagen">
        <small id="emailHelp" class="form-text text-muted">Pega un link</small>
      </div>
      <div class="form-group">
        <label for="descripcion">Ingresa una descripción de tu tarea</label>
        <input type="text" class="form-control" v-model="descripcion">
        <small id="emailHelp" class="form-text text-muted">Escribe aquí</small>
      </div>
      <button type="submit" class="btn btn-primary bg-info">Agregar tarea</button>
  </form>
    
  </div>
</template>

<script>
  export default {
    name: 'Tareas',
    data() {
      return {
        tarea: '',
        imagen: '',
        descripcion: ''
      }
    },
    methods: {
      enviarTareas(){
        if (this.tarea && this.imagen && this.descripcion) {
          let listaTareas = {
            tarea: this.tarea,
            imagen: this.imagen,
            descripcion: this.descripcion
        };
        this.$emit('enviandoTareas', listaTareas);
        this.titulo = "";
        this.imagen = "";
        this.descripcion = "";
        }
      }  
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
  width: 50%;
  margin-left: 50px;
  margin-top: 50px;
}

</style>

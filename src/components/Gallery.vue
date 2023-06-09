<template>
  <div>
    <div id="divCardGallery" class="card mt-4">
      <div class="card-header text-center">Galería</div>
      <!-- v-for:para mostrar cada imagen del array de objetos definidos en "App.vue" -->
      <div
        v-for="(imagen, index) of galeria"
        :key="index"
        class="text-center m-2"
      >
      <!-- Evento click que ejecuta el método "mostrarDescripcion" y recibe el index -->
        <img
          @click="mostrarDescripcion(index)"
          :src="imagen.src"
          class="card-img-top rounded w-75 mt-3"
          alt="imagen"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "gallery-component",
  props: {
    //Recibo el dato de App.vue
    galeria:{
        type: Array,
        required: true,
    }
  },
  data: function () {
    return {
    };
  },
  // computed: {},
  methods: {
    //Método que emite el evento al componente padre.
    mostrarDescripcion(index) {
      this.$emit("eventMostrarDesc", index)
    },
  },
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
#divCardGallery {
  max-height: 28.125rem;
  /* Muestra las imagenes con un scroll */
  overflow: auto;
}
</style>
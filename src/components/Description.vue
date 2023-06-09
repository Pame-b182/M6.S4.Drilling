<template>
    <div>
        <div id="divCardDescription" class="card mt-4">
            <div class="card-header">Descripción</div>
            <div class="row mt-5">
                <div class="col col-md-6">
                <div class="p-2">
                    <img :src="imgSeleccionada.src" class="card-img-top rounded" alt="imagen">
                </div>
                <div class="m-2 text-center">
                    Autor: {{imgSeleccionada.author}}
                </div>
                <div class="text-center m-5">
                    <button @click="cerrarDesc" type="button" class="btn btn-secondary">Cerrar</button>
                </div>
            </div>
            <div class="col col-md-6">
                <textarea rows="13" cols="27" :value="imgSeleccionada.description"></textarea>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: "description-component",
  props: {
    //Recibo el dato de app.vue
    imgSeleccionada:{
        type: Object,
        required: true,
    }
  },
  data: function () {
    return {};
  },
  // computed: {},
  methods: {
    cerrarDesc(){
        this.$emit("cerrarDesc");
    }
  }
  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  // -- End Lifecycle Methods
};
</script>

<style scoped>
#divCardDescription{
    height: 28.125rem;
}
</style>
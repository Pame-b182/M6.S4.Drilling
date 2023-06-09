<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col col-md-5">
        <!-- Al componente Gallery le debo pasar tbn la prop "galeria" e igualarlo a "gallery" de este archivo -->
        <!-- También debo pasarle el evento personalidado "@eventMostrarDesc" que viene del componente "Description"
        y ponerle el método de este archivo, que recibirá el evento personalidado -->
        <Gallery
        :galeria= "gallery"
        @eventMostrarDesc="mostrardesc"/>
      </div>
      <!-- v-if: si el src de cada objeto del array "gallery" es distinto a indefinido, se muestra el div -->
      <div class="col col-md-7" v-if="selectedImg.src !== undefined">
        <Description 
        :imgSeleccionada="selectedImg"
        @cerrarDesc="closeDesc"/>
      </div>
    </div>
  </div>
</template>

<script>
import Gallery from "@/components/Gallery.vue"
import Description from "@/components/Description.vue"

export default {
  name: "App",
  data: function(){
    return{
      gallery: [
        {
          src: "https://picsum.photos/id/602/300/200",
          author: "Autor Imagen 1",
          description:
            "1Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus. 1Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus.",
        },
        {
          src: "https://picsum.photos/id/603/300/200",
          author: "Autor Imagen 2",
          description:
            "2Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus.2Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus.",
        },
        {
          src: "https://picsum.photos/id/604/300/200",
          author: "Autor Imagen 3",
          description:
            "3Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus. 3Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus.",
        },
        {
          src: "https://picsum.photos/id/605/300/200",
          author: "Autor Imagen 5",
          description:
            "4Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus. 4Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut excepturi voluptatibus sint et adipisci recusandae quibusdam voluptas ipsum vitae quam eius asperiores unde nemo, hic voluptates aliquid est dolore temporibus.",
        },
      ],
      /*Se crea el dato "selectedImg", que será el que pase los datos de cada objeto 
      en el array "Gallery" al método "mostrarDesc" */
      selectedImg:{}
    }
  },
  methods:{
    mostrardesc(index){
      this.selectedImg=this.gallery[index];
    },
    closeDesc(){
      this.selectedImg={};
    }
  },
  components: {
    Gallery,
    Description,
  },
};
</script>

<style>

</style>

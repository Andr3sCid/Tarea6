<script>
import NavbarPrincipal from "./NavbarPrincipal.vue";

export default {
  components: {
    NavbarPrincipal,
  },

  data: function () {
    return {
      comidas: [
        {
          id: 1,
          nombre: "Hamburguesa",
          precio: 13000,
          categoria: "Hambusguesas",
          img: "https://images.aws.nestle.recipes/resized/69772e52046d2550dab03cd6b73c3c32_Hamurguesa_Estilo_york_1200_600.jpg",
        },
        {
          id: 2,
          nombre: "Papas fritas",
          precio: 1200,
          categoria: "Papas",
          img: "https://www.todofrio.cl/wp-content/uploads/2021/06/chipsweb.jpg",
        },
        {
          id: 3,
          nombre: "Fideos con salsa",
          precio: 5000,
          categoria: "Pastas",
          img: "https://recetasfideos.pro/wp-content/uploads/2021/01/fideos-con-salsa-cremosa-de-tomate.jpg",
        },
      ]
    };
  }
};
</script>

<template>
  <NavbarPrincipal></NavbarPrincipal>
  <b-container>
  <b-carousel
    id="carousel-fade"
    style="text-shadow: 0px 0px 2px #000"
    fade
    indicators
    img-width="1024"
    img-height="480"
    v-for="comida in comidas" :key="comida.id"
  >
    <b-carousel-slide
      caption={{comida.nombre}}
      img-src={{comida.img}}
    ></b-carousel-slide>
  </b-carousel>

    <b-row>
      <b-col v-for="comida in comidas" :key="comida.id">
        <b-card id="card-presentacion" class="shadow p-3 mb-5 bg-body rounded">
          <b-img
            thumbnail
            fluid
            id="img-carg"
            :src="`${comida.img}`"
            alt="imagen-comida"
            img-top
          ></b-img>
          <b-card-text>
            <div>
              {{ comida.nombre }}
              <div>${{ comida.precio }}</div>
            </div>
            <div>
              <button id="btn-agregarCarrito">+</button>
            </div>
          </b-card-text>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<style>
#card-presentacion {
  width: 250px;
  height: 300px;
  background-color: #a74ac7;
}
</style>
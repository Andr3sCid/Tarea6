<script>
export default {
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
      ],
    };
  },
};
</script>

<template data-="datos">
  <div id="navbar">

    <b-dropdown text="Categoria" variant="primary" class="m-2">
       <div v-for="comida in comidas" :key="comida.id">
         <b-dropdown-item href="#"><p>{{comida.categoria}}</p></b-dropdown-item>
       </div>
    </b-dropdown>

    <b-card>
      <div>
        <b-button v-b-toggle:my-collapse>
          <span class="when-open">Cerrar</span
          ><span class="when-closed">Abrir</span> Carrito de compra
        </b-button>
        <b-collapse id="my-collapse">
          <!-- Content here -->
          <div class="mt-2">This is data that's being collapsed</div>
        </b-collapse>
      </div>
    </b-card>
  </div>
</template>

<style>
#navbar {
  width: 100%;
  height: 20%;
  display: flex;
  justify-content: space-around;
  background-color: #920689;
}

#btn-categorias {
  background-color: #e858ab;
}
</style>
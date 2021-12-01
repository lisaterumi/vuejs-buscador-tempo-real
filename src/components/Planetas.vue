<template>
   <div class="container cont">

    <div class="row">

      <div class="col-md-12">
      
        <h1>Buscador em tempo Real com Vue JS - Planetas do Sistema Solar</h1> 
        
        <input type="text" v-model="buscar" class="form-control" placeholder="Exemplo: Saturno"/>              

      </div>

    </div>

    <div class="row mt-3">

      <div class="col-md-4" v-for="item in items" v-bind:key="item.id"> 

        <div class="card mb-3">
          <img class="card-img-top" v-bind:src="'img/' + item.img" v-bind:alt="item.nome">
          <div class="card-body">
            <h3 class="card-title mb-3">{{ item.nome }}</h3>
            <p class="card-text">
              <strong>Tipo:</strong> {{ item.tipo }} 
            </p>
            <p class="card-text">
              <strong>Raio equador (km):</strong> {{ item.raio }} 
            </p>
            <p class="card-text">
              <strong>Distância sol:</strong> {{ item.distancia }} 
            </p>
            <p class="card-text">
              <strong>Satélites:</strong> {{ item.satelites }} 
            </p>
            <p class="card-text">
              <strong>Período de rotação:</strong> {{ item.rotacao }} 
            </p>
            <p class="card-text">
              <strong>Período de translação:</strong> {{ item.translacao }} 
            </p>
          </div>
        </div>

      </div>

    </div>

   </div>
</template>

<script>

import datos from "../assets/json/planetas.json";

export default {

  // Exportando o compomente 'Planetas' 
  name: 'Planetas',
  props: {
    msg: String
  },
  
  // declarando o elemento de busca
  data() {
    return {
      buscar: ''
    }
  },
    
  // Método 'items' que obtem os dados dos planetas
  // Filtrando a busca com o método filter()  
  computed: {
    items() {
      return datos.filter(item => {
        return item.nome.toLowerCase().includes(this.buscar.toLowerCase());
      });
    },

  }
  
}

</script>

<style scoped>
  /**/
</style>

<template>
  <section class="container">
    <div class="header">
      <h1>Star Wars Planets</h1>
      <b-button class="mb-3" to="/" href="#" variant="outline-dark">
        Voltar
      </b-button>
    </div>
    <div class="boxCard">
      <!-- Lista as informações dos planetas-->
      <b-list-group
        v-for="(item, index) in planets"
        :key="index"
        class="mb-2"
        bg-variant="dark"
        text-variant="warning"
      >
        <b-list-group-item class="bg-dark text-warning">
          <b-card-title @click="exibirInfo(index)">
            {{ item.name }}
          </b-card-title>
        </b-list-group-item>
        <!--verifica se o index selecionado é o mesmo que esta aberto-->
        <div v-if="artigoAberto === index">
          <b-list-group-item class=" bg-warning">
            <div class="bg-warning text-dark">
              <strong>Rotation period:</strong>
              {{ item.rotation_period }}
            </div>
            <div class=" bg-warning text-dark">
              <strong>Orbital period:</strong> {{ item.orbital_period }}
            </div>
            <div class=" bg-warning text-dark">
              <strong>Diameter:</strong> {{ item.diameter }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Climate:</strong> {{ item.climate }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Gravity:</strong> {{ item.gravity }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Terrain:</strong> {{ item.terrain }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Surface water:</strong> {{ item.surface_water }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Population:</strong> {{ item.population }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Residents:</strong> {{ item.residents }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Created:</strong> {{ item.created }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Edited:</strong> {{ item.edited }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Url:</strong> {{ item.url }}
            </div>
          </b-list-group-item>
        </div>
      </b-list-group>
      <div class="footer">
        <h5>Todos os direitos</h5>
      </div>
    </div>
  </section>
</template>

<script>

import axios from '~/plugins/swapi'

export default {
  // importa informações swapi planetas
  asyncData () {
    return axios.get('planets/').then(response => ({
      planets: response.data.results
    }))
  },
  data () {
    return {
      artigoAberto: []
    }
  },
  methods: {

    /* metodo para exibir mais informações */
    exibirInfo (index) {
      this.artigoAberto = index
    }

  }
}
</script>

<style>

</style>

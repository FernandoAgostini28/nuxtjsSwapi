<template>
  <section class="container">
    <div class="header">
      <h1>Star Wars People</h1>
      <b-button class="mb-3" to="/" href="#" variant="outline-dark">
        Voltar
      </b-button>
    </div>
    <div class="boxCard">
      <!-- Lista as informações dos pessoas-->
      <b-list-group
        v-for="(item, index) in people"
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
              <strong>Height:</strong>
              {{ item.height }}
            </div>
            <div class=" bg-warning text-dark">
              <strong>Mass:</strong> {{ item.mass }}
            </div>
            <div class=" bg-warning text-dark">
              <strong>Hair color:</strong> {{ item.hair_color }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Skin color:</strong> {{ item.skin_color }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Eye_color:</strong> {{ item.eye_color }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Birth year:</strong> {{ item.birth_year }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Gender:</strong> {{ item.gender }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Homeworld:</strong> {{ item.homeworld }}
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
  // importa informações swapi pessoas
  asyncData () {
    return axios.get('people/').then(response => ({
      people: response.data.results
    }))
  },
  data () {
    return {
      artigoAberto: []
    }
  },
  methods: {

    /* metodo para  exibir informações */
    exibirInfo (index) {
      this.artigoAberto = index
    }

  }
}
</script>

<style>

</style>

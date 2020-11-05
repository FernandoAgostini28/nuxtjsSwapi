<template>
  <div class="container">
    <div class="header">
      <h1>Star Wars Films</h1>
      <b-button class="mb-3" to="/" href="#" variant="outline-dark">
        Voltar
      </b-button>
    </div>
    <div class="boxCard">
      <!-- Lista as informações dos filmes-->
      <b-list-group
        v-for="(item, index) in films"
        :key="index"
        class="mb-2 "
        bg-variant="dark"
        text-variant="warning"
      >
        <b-list-group-item class="bg-dark text-warning">
          <b-card-title @click="exibirInfo(index)">
            {{ item.title }}
          </b-card-title>
        </b-list-group-item>
        <!--verifica se o index selecionado é o mesmo que esta aberto-->
        <div v-if="artigoAberto === index">
          <b-list-group-item class=" bg-warning">
            <div class="bg-warning text-dark">
              <strong>Opening Crawl:</strong>
              {{ item.opening_crawl }}
            </div>
            <div class=" bg-warning text-dark">
              <strong>Episode:</strong> {{ item.episode_id }}
            </div>
            <div class=" bg-warning text-dark">
              <strong>Director:</strong> {{ item.director }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Producer:</strong> {{ item.producer }}
            </div>
            <div class="bg-warning text-dark">
              <strong>Release Date:</strong> {{ item.release_date }}
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
  </div>
</template>

<script>
import axios from '~/plugins/swapi'

export default {
  // importa informações swapi filmes
  asyncData () {
    return axios.get('films/').then(response => ({
      films: response.data.results
    }))
  },
  data () {
    return {
      artigoAberto: []
    }
  },
  methods: {

    /* metodo para exibir informações */
    exibirInfo (index) {
      this.artigoAberto = index
    }

  }
}
</script>

<style>

</style>

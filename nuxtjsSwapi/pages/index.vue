<template>
  <div class="container">
    <div class="header">
      <h1>Star Wars</h1>      
    </div>
    <div class="boxCard">
      <b-card  bg-variant="dark" text-variant="warning" title="Pessoas">
       <b-card-text>
          With supporting text below as a natural lead-in to additional content.
        </b-card-text>
        <b-button to="/pessoas" href="#" variant="outline-warning">Conhecer</b-button>
      </b-card>
    </div>
    <div class="boxCard">
      <b-card bg-variant="dark" text-variant="warning" title="Planetas">
       <b-card-text>
          With supporting text below as a natural lead-in to additional content.
        </b-card-text>
        <b-button to="/planetas" href="#" variant="outline-warning">Conhecer</b-button>
      </b-card>
    </div>
    <div class="boxCard">
      <b-card bg-variant="dark" text-variant="warning" title="Filmes">
       <b-card-text>
          With supporting text below as a natural lead-in to additional content.
        </b-card-text>
        <b-button to="/filmes" href="#" variant="outline-warning">Conhecer</b-button>
      </b-card>
    </div>
    <div class="footer">
      <h5>Todos os direitos</h5>
    </div>
  </div>   
</template>

<script>
import axios from "../plugins/swapi"

export default {
}
</script>

<style>


</style>
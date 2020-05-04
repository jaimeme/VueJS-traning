<template>
  <!--
    <br />
    <container-b>
      <p v-for="item in lista" :key="item.id">Nome do usuário {{item.id}}: {{item.nome}}</p>
  -->

  <!--está sendo usado item.id ao invés do lsita.id por causa que está dentro da lógica v-for (foreach) -->
  <!--

      <img :src="importLogo()" />
    </container-b>
  -->
  <b-container>
    <b-row>
      <b-button>teste</b-button>
      <b-col sm="4" v-for="pokemon in pokemons" :key="pokemon.id">
        <img v-bind:src="pokemon.sprite" />
        <p>{{ pokemon.name }}</p>
        {{console.log(pokemon.name)}}
      </b-col>
    </b-row>
  </b-container>
</template>
<script>
export default {
  methods: {
    importLogo() {
      return require("../assets/logo.png");
      //feito uma importação de arquivo por método
    },
    fetchPokemon() {
      let url =
        "https://pokeapi.co/api/v2/pokemon?offset=${this.results}&limit=${{this.results + 6}}";
      this.pokemons = [];
      fetch(url)
        .then(res => res.json())
        .then(response => {
          response.results.forEach(pokemon => {
            let data = {};
            data.name = pokemon.name;
            fetch(pokemon.url)
              .then(res => res.json())
              .then(pokemonData => {
                data.id = pokemonData.id;
                data.sprite = pokemonData.sprites.front_default;
              });
            this.pokemons.push(data);
          });
        });
    },
    monted() {
      this.fetchPokemon();
    }
  },
  data() {
    return {
      lista: [
        { id: 1, nome: "Jaime" },
        { id: 2, nome: "João" },
        { id: 3, nome: "Jadson" }
      ],
      pokemons: [],
      results: 0
    };
  },
  name: "Lista"
};
</script>
<style scoped>
.pokemons {
  background-color: antiquewhite;
}
p {
  color: #01a880; /* css aplicado somente a este template */
}
</style>



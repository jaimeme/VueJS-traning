<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>{{contador}}</h3>
    <br />
    <button @click="acrescentar()">Clique aqui</button> Para acrescentar
    <!--V-on pode ser substituido por "@" no exemplo acima ficou >> @click (V-on:click) -->
    <!--V-bind pode ser substituido por ":" -->
    <br />
    <br />
    <button @click="diminuir()">Clique aqui</button> Para diminuir
  </div>
</template>

<script>
export default {
  methods: {
    acrescentar() {
      this.contador++;
      this.contador >= 10 ? (this.msgSecret = true) : null;
      //operador ternário com else null
    },
    diminuir() {
      this.contador--;
      this.contador < 10 ? (this.msgSecret = false) : null;
    }
  },
  data() {
    return {
      contador: 0,
      msgSecret: false
    };
  },
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

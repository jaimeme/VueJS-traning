<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>{{contador}}</h3>
    <br />
    <button @click="acrescentar()">Clique aqui</button> Para acrescentar
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
    },
    diminuir() {
      this.contador--;
    }
  },
  data() {
    return {
      contador: 0,
      dez: false,
      difDez: false
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

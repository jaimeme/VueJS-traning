<template>
  <section>
    <b-container>
      <br />
      <p v-for="item in lista" :key="item.id">Nome do usuário {{item.id}}: {{item.nome}}</p>
      <!--está sendo usado item.id ao invés do lsita.id por causa que está dentro da lógica v-for (foreach) -->
      <img :src="importLogo()" />
    </b-container>
  </section>
</template>


<script>
export default {
  data() {
    return {
      lista: [
        { id: 1, nome: "Jaime" },
        { id: 2, nome: "João" },
        { id: 3, nome: "Jadson" }
      ]
    };
  },
  methods: {
    importLogo() {
      return require("../assets/logo.png");
    }
  },
  name: "Lista"
};
</script>

<style scoped>
p {
  color: #01a880; /* css aplicado somente a este template */
}
</style>

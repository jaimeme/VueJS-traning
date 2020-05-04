<template>
  <section>
    <b-container>
      <br />
      <p v-for="item in lista" :key="item.id">Nome do usuário {{item.id}}: {{item.nome}}</p>
      <!--está sendo usado item.id ao invés do lsita.id por causa que está dentro da lógica v-for (foreach) -->
      <img :src="importLogo()" />

      <div>
        <!-- vue animação -->
        <button @click="mostrar = !mostrar">Clique aqui</button>
        <transition name="cor">
          <p v-if="mostrar">Oiiiiiiiiiiiiiiiiiiiii</p>
        </transition>
      </div>
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
      ],
      mostrar: true
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
/* animação  1*/
.cor-enter-active,
.cor-leave-active {
  animation: cor 0.5s ease-in;
}

@keyframes cor {
  0% {
    color: red;
  }
  50% {
    color: blue;
  }
  100% {
    color: red;
  }
}
</style>

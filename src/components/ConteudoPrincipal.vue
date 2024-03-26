<!-- <script lang="ts">
import { ref } from 'vue'
import SelecionarIngredientes from '../components/SelecionarIngredientes.vue'
import SuaLista from './SuaLista.vue'
export default {
  // Composition API
  setup() {
    const ingredientes = ref<string[]>([]);

    function adicionarIngrediente(ingrediente: string) {

      ingredientes.value.push(ingrediente)

    }

    function removerIngrediente(ingrediente: string) {
      ingredientes.value = ingredientes.value.filter(iList => ingrediente !== iList);
    }

    return{
      ingredientes,
      adicionarIngrediente,
      removerIngrediente
    }

  },
  components: { SelecionarIngredientes, SuaLista }

  //Options API
  // data() {
  //   return {
  //     ingredientes: [] as string[]
  //   }
  // },

  // components: { SelecionarIngredientes, SuaLista },
  // methods: {
  //   adicionarIngrediente(ingrediente: string) {

  //     this.ingredientes.push(ingrediente)

  //   },

  //   removerIngrediente(ingrediente: string) {
  //     this.ingredientes = this.ingredientes.filter(iList => ingrediente !== iList);
  //   }
  // }
}
//"SelecionarIngredientes" as "SelecionarIngredientes" | "MostrarReceitas"
</script> -->

<!-- <script setup lang="ts">
import { ref } from 'vue'
import SelecionarIngredientes from '../components/SelecionarIngredientes.vue'
import SuaLista from './SuaLista.vue'

    const ingredientes = ref<string[]>([]);

    function adicionarIngrediente(ingrediente: string) {

      ingredientes.value.push(ingrediente)

    }

    function removerIngrediente(ingrediente: string) {
      ingredientes.value = ingredientes.value.filter(iList => ingrediente !== iList);
    }

</script> -->

<script lang="ts">
import SelecionarIngredientes from '../components/SelecionarIngredientes.vue'
import SuaLista from './SuaLista.vue'
type Pagina = "SelecionarIngredientes" | "MostrarReceitas";
import MostrarReceitas from './MostrarReceitas.vue';
export default {
  data() {
    return {
      ingredientes: [] as string[],
      conteudo: "SelecionarIngredientes" as Pagina
    }
  },

  components: { SelecionarIngredientes, SuaLista, MostrarReceitas },
  methods: {
    adicionarIngrediente(ingrediente: string) {

      this.ingredientes.push(ingrediente)

    },

    removerIngrediente(ingrediente: string) {
      this.ingredientes = this.ingredientes.filter(iList => ingrediente !== iList);
    },
    navegar(pagina: Pagina){
      this.conteudo = pagina
    }
  }
}

</script>

<template>
  <main class="conteudo-principal">
    <SuaLista :ingredientes="ingredientes" />
    <SelecionarIngredientes v-if="conteudo === 'SelecionarIngredientes'" @adicionar-ingrediente="adicionarIngrediente"
      @remover-ingrediente="removerIngrediente" @buscar-receitas="navegar('MostrarReceitas')" />
    <MostrarReceitas v-else-if="conteudo === 'MostrarReceitas'" />
  </main>
</template>

<style scoped>
.conteudo-principal {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #FFFAF3);
  color: var(--cinza, #444);

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}

@media only screen and (max-width: 1300px) {
  .conteudo-principal {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .conteudo-principal {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}
</style>
<script lang="ts">
import Banner from './components/Banner.vue'
import ConteudoPrincipal from './components/ConteudoPrincipal.vue';
import Rodape from './components/Rodape.vue';
export default {
  components: { Banner,ConteudoPrincipal,Rodape }
}
// export default {
//   components: {Banner:Banner}
// }
</script>

<template>
  <Banner />
  <ConteudoPrincipal />
  <Rodape/>
  <!-- <h1 class="titulo">
    Texto do app.vue
  </h1> -->
</template>

<!-- <style scoped>
.titulo{
  color:red;
}
</style> -->
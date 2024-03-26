<script lang="ts">
import Banner from './components/Banner.vue'
import ConteudoPrincipal from './components/ConteudoPrincipal.vue';

export default {
  components: { Banner,ConteudoPrincipal }
}
// export default {
//   components: {Banner:Banner}
// }
</script>

<template>
  <Banner />
  <ConteudoPrincipal />
  <!-- <h1 class="titulo">
    Texto do app.vue
  </h1> -->
</template>

<!-- <style scoped>
.titulo{
  color:red;
}
</style> -->
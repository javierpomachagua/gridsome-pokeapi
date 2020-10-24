<template>
  <Layout>
    <div
      class="bg-blue-500 rounded-lg flex flex-col items-center justify-center p-8"
    >
      <h1 class="text-lg font-semibold mb-4">
        Escogiste a
        <span class="text-xl text-green-300 uppercase font-bold">{{
          $page.pokemon.name
        }}</span>
      </h1>
      <div
        class="w-32 h-32 rounded-full bg-white border-purple-600 border-2 border-solid p-2 mb-4"
      >
        <img :src="$page.pokemon.image" alt="" />
      </div>
      <g-link
        to="/pokedex"
        class="bg-yellow-500 rounded-lg font-bold text-md px-4 py-2"
      >Regresar</g-link>
    </div>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  pokemon(id: $id) {
    id
    name
    image
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      name: this.$page.pokemon.name
    }
  }
}
</script>

<style>

</style>
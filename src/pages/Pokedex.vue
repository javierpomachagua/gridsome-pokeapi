<template>
  <Layout>
    <div
      class="bg-blue-500 rounded-lg flex flex-col items-center justify-center p-5 space-y-5"
    >
      <h1 class="text-lg font-semibold text-white uppercase">
        ¡Elige tu primer Pokemón!
      </h1>
      <div class="flex flex-wrap">
        <g-link
          :to="`/pokemon/${edge.node.id}`"
          v-for="edge in $page.pokemons.edges"
          :key="edge.node.id"
          class="m-2 flex flex-col items-center"
        >
          <div class="w-20 h-20 p-2 border-purple-600 border-2 border-solid rounded-full bg-white">
            <img :src="edge.node.image" alt="" class="object-cover" />
          </div>

          <p class="font-semibold capitalize">{{ edge.node.name }}</p>
        </g-link>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query {
  pokemons: allPokemon {
    edges {
      node {
        id
        name,
        image
      }
    }
  }
}
</page-query>

<style>

</style>
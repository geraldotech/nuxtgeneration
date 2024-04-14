<script setup>
/* const route = useRoute();

console.log(route.params.id) */

// context nuxt

const nuxt = useNuxtApp()
console.log(nuxt)


</script>

<template>
  <div>
    event id: {{ $route.params.id }}
  </div>
</template>
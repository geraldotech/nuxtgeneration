<script setup>
const route = useRoute()

const postSlug = route.params.slug

const single = await fetch(`https://api-restful-json.vercel.app/entregasuporte?slug_like=${postSlug}`).then((req) => req.json())

// Destructuring the single object
const { id, title, question, slug, answer } = single[0] ? single[0] : 'not found'
</script>
<template>
  <div v-if="single[0]">
    <h1>{{ id }} - {{ title }}</h1>
    <h2>{{ question }}</h2>
    <h3>{{ answer }}</h3>
  </div>

  <h1 v-if="!single[0]">Post not found!</h1>
</template>

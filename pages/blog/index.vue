
<script setup>

const posts = await fetch("https://api-restful-json.vercel.app/entregasuporte").then(req => req.json())

//console.log(posts)
</script>

<template>
  <h1>Blog posts</h1>
  <div v-for="post in posts"> 
 <p>
  <NuxtLink :to="`/blog/${post.slug}`">{{ post.id }} - {{ post.title }}</NuxtLink>
 </p>
  </div>
</template>
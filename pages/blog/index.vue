<script setup>
// enabling cache
const nuxtApp = useNuxtApp()

const url = 'https://api-restful-json.vercel.app/entregasuporte'
// const posts = await fetch("https://api-restful-json.vercel.app/entregasuporte").then(req => req.json())

// version with cache
const { data } = await useFetch(url, {
  headers: {
    Accept: 'application/json',
  },
  transform(input) {
    return {
      ...input,
      fetchAt: new Date(),
    }
  },
  getCachedData(key) {
    // return nullish value -> refetch the data
    return nuxtApp.payload.data[key] || nuxtApp.static.data[key]
  },
})

//console.log(data.value[0].title)

</script>

<template>
  <h1>Blog posts</h1>
  <!--   <div v-for="post in posts"> 
 <p>
  <NuxtLink :to="`/blog/${post.slug}`">{{ post.id }} - {{ post.title }}</NuxtLink>
 </p>
  </div> -->

  <div v-for="post in data">
    <p>
      <NuxtLink :to="`/blog/${post.slug}`">{{ post.id }}  {{ post.title }}</NuxtLink>
    </p>
  </div>
</template>

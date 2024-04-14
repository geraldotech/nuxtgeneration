
<script setup>
// enabling cache
const nuxtApp = useNuxtApp()

const jsonplace = 'https://jsonplaceholder.typicode.com/posts/?_limit=10'

// jokes needs headers app/json
// with cache return same joke no fetch again
// https://www.youtube.com/watch?v=aQPR0xn-MMk
const jokes = 'https://icanhazdadjoke.com'

const {data} = await useFetch(jokes, {
  headers:{
    Accept: 'application/json'
  },
  transform(input){
    return {
      ...input,
      fetchAt: new Date()
    }
  },
  getCachedData(key){
    // return nullish value -> refetch the data
   return nuxtApp.payload.data[key] || nuxtApp.static.data[key]
  
}
})






</script>


<template>
  <div>
    <h1>Posts page</h1>
    <p>{{  data.joke}}</p>
    
  </div>
</template>
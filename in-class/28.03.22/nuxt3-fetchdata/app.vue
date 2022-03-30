<template>
  <div>
    <nav> add a nav bar here</nav>
    
  <header>
     <h1>API Test Land</h1>
  </header>
  <main> 
    <NuxtPage />
 
      <p>Page Visits: {{ data }}</p>

      <p v-for="muppet in muppets" :key="muppet.id">
        {{ muppet.name }} -- {{ muppet.type }}
      </p>
      </main>
      <footer>add a footer here </footer>
  </div>
</template>

<script setup>
const { data } = await useAsyncData("count", () => $fetch("/api/count"));

const { data: muppets } = await useAsyncData("muppets", () =>
  $fetch("/api/muppets"),
);



</script>

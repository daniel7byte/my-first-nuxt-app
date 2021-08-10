<template>
  <div class="container">
    <img :src="planet.image"/>
    <h1>Dynamic Page - {{ planet.title }}</h1>
    <pre>
      {{ $data }}
    </pre>
  </div>
</template>

<script>
export default {
  async asyncData ({ params }) {
    const planet = await fetch(
      `https://api.nuxtjs.dev/planets/${params.slug}`
    ).then((res) => res.json())
    return { planet }
  }
}
</script>

<style>
h1 {
  font-size: 2em;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
img {
  height: 250px;
}
</style>

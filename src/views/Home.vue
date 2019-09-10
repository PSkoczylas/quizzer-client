<template>
  <div class="home">
    <div v-for="category in categories" v-bind:key="category.name">
      <p>name: {{category.name}} description: {{category.description}}</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  data() {
    return {
      categories: []
    }
  },
  created() {
    axios.get('/categories/')
    .then(response => (
      this.categories = response.data
    )).catch(error => console.log(error))
  },
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>

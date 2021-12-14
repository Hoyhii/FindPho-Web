<template>
  <div class="home">
    <button @click="getData">Nyomjál</button>
    <Background msg='gogogo' />
      <div>
        <div v-for="post in posts" v-bind:key="post.id">
          <h2>{{ post.title }}</h2>
          <p>{{ post.content }}</p>
        </div>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Background from '@/components/Background.vue'

export default {
  data () {
    return {
      posts: []
    }
  },
  name: 'Home',
  components: {
    Background
  },
  methods: {
    async getData () {
      console.log('itt')
      try {
        fetch('http://127.0.0.1:8000')
          .then(response => console.log(response))
          .then(data => console.log(data))
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>
<style scoped>
  h1{
    color:white
  }
</style>

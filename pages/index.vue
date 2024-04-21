<template>
  <div>
    <navbar/>
    <Thisisarticle :articles="article" />
  </div>
</template>

<script>
import Thisisarticle from '../components/thisisarticle.vue'
import navbar from '../components/navbar.vue'

export default {
  name: 'IndexPage',
  components: {
    Thisisarticle,
    navbar,
  },
  data() {
    return {
      article: [],
    }
  },
  async fetch() {
    await this.getArticles()
  },
  methods: {
    async getArticles() {
      try {
        const resp = await this.$axios.$get('https://dev.to/api/articles/')
        this.article = resp
      } catch (error) {
        console.error('Error:', error)
        this.article = []
      }
    },
  },
}
</script>

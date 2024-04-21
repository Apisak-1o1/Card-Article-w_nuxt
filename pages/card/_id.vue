<template>
    <main>
        <div>
            <insidearc v-if="article " :articles="article"/>
        </div>
    </main>
</template>

<script>
import navbar from '@/components/navbar.vue'
import insidearc from '../../components/insidearc.vue'

export default {
    name:'cardpages',
    components: {
    navbar,
    insidearc,
  },
  data() {
    return {
      article: null,
    }
  },
  async mounted () {
    console.log(this.$route)
    
    await this.getArticles()
    },

    methods: {
    async getArticles() {
      try {
        const idarticle = this.$route.params.id
        const resp = await this.$axios.$get('https://dev.to/api/articles/'+ idarticle)
        this.article = resp
      } catch (error) {
        console.error('Error:', error)
        this.article = []
      }
    },
    },
  }
</script>


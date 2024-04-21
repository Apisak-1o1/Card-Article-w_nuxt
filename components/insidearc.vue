<template>
  <main>
    <div class="more">
        <div>
            <navbar/>
            <img :src="articles.cover_image ? articles.cover_image : 'https://cdn4.iconfinder.com/data/icons/picture-sharing-sites/32/No_Image-1024.png'" alt="image">
            <h1>{{ articles.title }}</h1>
            <span v-html="articles.body_html ? articles.body_html :'There is no more desciption here!'"></span>
        </div>
    </div>
  </main>
</template>

<script>
import Navbar from './navbar.vue'
export default {
  name: 'insidearc',
  components:{
    Navbar 
  },
     
    props: {
    articles: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style>
main{
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    height: 100%;
}

.more{
    display: flex;
    justify-content: center;
    align-content: center;
    width: 100%;
    height: 100%;
    text-align: center;
    overflow: hidden;
    border-radius: 1vh 1vh 1vh 1vh;
    margin: 4.2vh;
    box-shadow: 1vh 1vh 0.5vh;
    border: solid grey 0.2px;
}
.more img{
    overflow: hidden;
    width: 50%;
    height: auto;
}</style>

<template>
  <main>
    <div v-for="item in articles" :key="item.id" class="loop">
        <span class="card" @click="$router.push(`/card/${item.id}`)">
            <img :src="item.cover_image ? item.cover_image : 'https://cdn4.iconfinder.com/data/icons/picture-sharing-sites/32/No_Image-1024.png'" alt="image">
            <h6>{{ item.title }}</h6>
             <span v-html="item.description  ? item.description  :'There is no more desciption here!'"></span>
        </span>
    </div>
  </main>
</template>

<script>
export default {
  name: 'Thisisarticle',
  props: {
    articles: {
      type: Array,
      default: () => [],
    },
  },
}
</script>

<style>
main{
    display: flex;
  flex-wrap: wrap;
}

.card{
    display: flex;
    justify-content: space-between;
    align-content: space-between;
    width: 32vh;
    height: 32vh;
    text-align: center;
    overflow: hidden;
    border-radius: 1vh 1vh 1vh 1vh;
    margin: 4.2vh;
    box-shadow: 1vh 1vh 0.5vh;
    border: solid grey 0.2px;
}
.card img{
    overflow: hidden;
}
</style>
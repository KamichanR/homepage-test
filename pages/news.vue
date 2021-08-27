<template>
  <div class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      progress
      hide-delimiter-background
    >
      <v-carousel-item
        src="img/background/news.jpg"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto py-16">
          <v-container class="ma-auto white--text">
            <h1 class="text-center">Comming Soon...</h1>
          </v-container>
        </div>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [
        {
          title: '',
          subtitle: '',
          text: [
            '',
          ],
          image: ''
        },
      ]
    }
  },
  head() {
    return {
      title: '新着情報｜'
    }
  }
}
</script>

<style lang="scss" scoped>
#background {
  background-color: rgba($color: #000, $alpha: .5);
}

#content {
  position: absolute;
  margin: auto;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
}
</style>

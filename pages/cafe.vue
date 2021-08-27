<template>
  <div class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      progress
    >
      <v-carousel-item
        src="img/slideshow/cafe-slideshow/slide1.jpg"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto py-16">
          <v-container class="ma-auto white--text">

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
      mainCafes: [
        {
          name: '北大祭カフェ',
          image: 'hokudaisai'
        }
      ]
    }
  },
  head() {
    return {
      title: '開催カフェ｜'
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

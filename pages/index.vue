<template>
  <v-row justify="center" align="center">
    <v-carousel
      id="topSlideshow"
      class="ma-0"
      cycle
      interval="5000"
      progress
      :height="topSlideshowHeight"
      :show-arrows="false"
    >
      <v-carousel-item
        v-for="i of 5"
        :key="i"
      >
        <div id="slider__img__wrapper" class="fill-height">
          <img :id="'slider__img'+i" :src="'img/slideshow/top-slideshow/slide'+i+'.jpg'" :alt="'top-slideshow-'+i">
        </div>
      </v-carousel-item>
    </v-carousel>
    <v-container id="eyecatch__logo">
      <v-img
        contain
        max-height="640"
        max-width="640"
        src="img/eyecatch__logo.svg"
        alt="北大カフェプロジェクト"
        style="margin: auto;"
      ></v-img>
    </v-container>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      topSlideshowHeight: 0
    }
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.getTopSlideshowHeight)
  },
  mounted() {
    window.addEventListener('resize', this.getTopSlideshowHeight)
    this.getTopSlideshowHeight()
  },
  methods: {
    getTopSlideshowHeight() {
      this.topSlideshowHeight = parseInt(window.innerHeight) - 100
    }
  },
}
</script>

<style lang="scss" scoped>
#slider__img__wrapper {
  background-color: #000;
  display: inline-block;
  width: 100%;
}

#slider__img1,
#slider__img2,
#slider__img3,
#slider__img4,
#slider__img5 {
  display: block;
  height: 100%;
  object-fit: cover !important;
  opacity: .75;
  width: 100%;
}

#slider__img1 {
  object-position: 60% 50%;
}

#slider__img2 {
  object-position: 70% 50%;
}

#slider__img3 {
  object-position: 65% 50%;
}

#slider__img4 {
  object-position: 60% 50%;
}

#slider__img5 {
  object-position: 20% 50%;
}

#eyecatch__logo {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
}
</style>

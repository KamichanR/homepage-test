<template>
  <div id="cafeContainer" class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      hide-delimiter-background
      :show-arrows="false"
      progress
    >
      <v-carousel-item
        v-for="i of 5"
        :key="i"
        :src="'img/slideshow/top-slideshow/slide'+i+'.jpg'"
      >
        <div id="background" class="fill-height fill-width"></div>
      </v-carousel-item>
    </v-carousel>
    <v-img
      id="eyecatch"
      contain
      max-height="640"
      max-width="640"
      src="img/eyecatch__logo.svg"
      alt="北大カフェプロジェクト"
      class="fill-width"
    ></v-img>
  </div>
</template>

<style lang="scss" scoped>
#background {
  background-color: rgba($color: #000, $alpha: .5);
}

#eyecatch {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
}
</style>

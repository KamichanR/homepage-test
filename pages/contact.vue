<template>
  <div class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      hide-delimiters
      :show-arrows="false"
    >
      <v-carousel-item
        src="img/background/contact.jpg"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto py-16">
          <v-container class="ma-auto text-center white--text">
            <h1>お問合わせ先</h1>
            <p>
              ご用件のある方はこちらの
              <a ref="noreferrer noopener" class="orange--text" href="https://docs.google.com/forms/d/e/1FAIpQLSeIvoi_zLzKgNAPqHOzZv35EM8gEk4FeY7qaDcnpIhfgneOZw/viewform?usp=sf_link" target="_blank">
                Googleフォーム
              </a><br>
              または以下のメールアドレスにご連絡ください。
            </p>
            <p>
              メールアドレス<br>
              hokcafe☆gmail.com<br>
              （☆を@に変換してください）
            </p>
          </v-container>
        </div>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'お問い合わせ｜'
    }
  },
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

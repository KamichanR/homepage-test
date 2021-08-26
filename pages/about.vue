<template>
  <v-row justify="center" align="center">
    <v-carousel
      id="topSlideshow"
      class="ma-0"
      progress
      hide-delimiter-background
      :height="topSlideshowHeight"
    >
      <v-carousel-item>
        <div id="slider__img__wrapper" class="fill-height">
          <img id="slider__img" src="img/slideshow/about-slideshow/slide1.png" alt="about-slideshow-1">
        </div>

        <v-container id="description" class="px-16 white--text">
          <h1 class="text-center">あらゆる人との交流の場</h1>
          <p>
            北大カフェプロジェクトは、美味しい飲み物と皆様との交流を通して、心温まるカフェスペースを提供する学生団体です。
          </p>
          <p>
            札幌市民の方を始め、観光客、留学生など、多くの人が訪れる北海道大学の特色を活かし、手作りカフェを提供しています。世代や属性、大学と社会の垣根を越えた交流の場を創りたいという想いから、カフェを開催しています。
          </p>
          <p>
            2007年に学生と教職員の有志によって立ち上げられて以来、季節やイベントに合わせたカフェ、学内外の団体とのコラボカフェなどを開催し、ご好評を頂いています。
          </p>
        </v-container>
      </v-carousel-item>

      <v-carousel-item>
        <div id="slider__img__wrapper" class="fill-height">
          <img id="slider__img" src="img/slideshow/about-slideshow/slide2.png" alt="about-slideshow-2">
        </div>

        <v-container id="description" class="px-16 white--text">
          <h1 class="text-center">代表挨拶</h1>
          <p>
            こんにちは、2021年度カフェプロ代表2年のそーたです。
          </p>
          <p>
            今年度もコロナの影響で本来の目的のカフェ開催などできないかもしれません。だからと言って活動を自粛するのではなく、「今できる新しいことにいろいろ挑戦する」が僕が目指したいサークルの形です。
          </p>
          <p>
            傲慢かもしれませんが、このサークルのトップを担ううえでメンバー全員に楽しいと思ってもらえる団体を作ります。
            2021年度の活動報告を是非とも楽しみにお待ちください。
          </p>
          <p>
            今年度もゆるくてアットホームなカフェプロをどうぞよろしくお願いします。
          </p>
          <p class="text-right">代表 鵜飼奏汰</p>
        </v-container>
      </v-carousel-item>

      <v-carousel-item>
        <div class="fill-height overflow-auto relative">
          <div id="slider__img__wrapper" class="fill-height fixed">
            <img id="slider__img" src="img/slideshow/about-slideshow/slide3.png" alt="about-slideshow-3" style="z-index: 0;">
          </div>

          <v-container class="absolute fill-height px-8 white--text">
            <v-row>
              <v-col cols="12" style="z-index: 1;">
                <h1 class="text-center nowrap">カフェ開催までの流れ</h1>
              </v-col>
              <v-col
                v-for="(process, i) of processes"
                :key="i"
                cols="12"
                md="4"
              >
                <v-card>
                  <v-img :src="'img/processes/process'+(i+1)+'.png'"></v-img>
                  <div class="pa-2">
                    <h2 class="text-center">{{ process.subheading }}</h2>
                    <p>{{ process.text }}</p>
                  </div>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </div>
      </v-carousel-item>
    </v-carousel>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      topSlideshowHeight: 0,
      processes: [
        {
          subheading: '全体ミーティング',
          text: '開催したいカフェの概要についてメンバー全員と話し合い、テーマやコンセプトを大まかに決定します。そして、そのカフェの担当者を募集します。',
        },
        {
          subheading: '担当者ミーティング',
          text: '担当者は比較的少人数で構成されます。ここでは全体ミーティングで決定したカフェの概要を元に、どのような企画・メニュー・運営方法にするかを決定します。',
        },
        {
          subheading: '準備・開催',
          text: '当日のための材料・道具を準備・設置し、お客様を出迎える用意を整えます。当日はお客様がとの楽しんでいただけるカフェを全力で開催します。',
        }
      ]
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

#slider__img {
  display: block;
  height: 100%;
  object-fit: cover;
  object-position: 50% 50%;
  opacity: .6;
  width: 100%;
}

#description {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
}

#progress__img {
  object-fit: contain;
}
</style>

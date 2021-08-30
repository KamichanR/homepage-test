<template>
  <div class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      hide-delimiter-background
      progress
    >
      <v-carousel-item
        v-for="(mainCafe, i) in mainCafes"
        :key="i"
        :src="'img/slideshow/cafe-slideshow/'+mainCafe.background+'.jpg'"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto py-16">
          <v-container class="ma-auto white--text">
            <v-row>
              <v-col
                cols="12"
                md="8"
                class="ma-auto"
              >
                <p class="text-center ma-0">主要カフェ</p>
                <h1 class="text-center pb-4">{{ mainCafe.name }}</h1>
                <p
                  v-for="(text, j) in mainCafe.texts"
                  :key="j"
                >
                  {{ text }}
                </p>
              </v-col>
              <v-col
                cols="12"
                md="4"
              >
                <v-card
                  v-for="j of mainCafe.images"
                  :key="j"
                  class="my-4"
                >
                  <v-img
                    :src="'img/cafes/maincafes/'+mainCafe.background+'/image'+j+'.jpg'"
                  ></v-img>
                </v-card>
              </v-col>
            </v-row>
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
          background: 'hokudaisai',
          texts: [
            '例年6月に行われる北大祭に合わせて、北大祭期間中にカフェを開催しています。例年は総合博物館前のウッドデッキを会場にしています。ここからは緑広がる理学部ローンをご覧になれます。',
            '夏の暑い時期に開催されるカフェなので、冷たい飲み物がとても人気です。過去には北大カフェプロジェクトのオリジナルドリンクも提供していて、ご好評をいただきました。',
            '多数の音楽サークルさんともコラボしていて、味覚だけでなく聴覚でも楽しめるカフェを例年提供しています。',
            '小さいお子様からご高齢の方まで大変人気の高いカフェになっています。ぜひお越しください。'
          ],
          images: 3
        },
        {
          name: '銀杏並木カフェ',
          background: 'ityonamiki',
          texts: [
            '10月下旬から11月上旬に北大13条通りの銀杏がきれいに色づきます。毎年多くの方が北大名物の銀杏並木を見に来ています。この時期に13条交差点にて銀杏並木カフェを開催しています。',
            'この時期になると少し肌寒くなるので温かい飲み物を提供しています。特に夜のジャック・オー・ランタンはとてもきれいで秋を満喫できる空間になっています。',
            '学内の音楽サークルさんを多数招致して、カフェと同時に音楽演奏も楽しむことができます。'
          ],
          images: 3
        },
        {
          name: 'かまくらカフェ',
          background: 'kamakura',
          texts: [
            '2月上旬のまだ大学内に雪が降り積もっている頃、理学部ローンにてかまくらカフェを開催しております。',
            '来場者の方々と一緒にかまくらを作り、その中で飲み物を飲みながらゆったりとくつろぐ。そんな体験をしていただくことが出来ます。',
            'とても寒い中でのカフェなので温かい飲み物を提供しています。'
          ],
          images: 3
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

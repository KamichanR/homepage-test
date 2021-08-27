<template>
  <div class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      progress
    >
      <v-carousel-item
        src="img/slideshow/link-slideshow/slide1.jpg"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto py-16">
          <v-container class="ma-auto white--text">
            <h1 class="text-center">共同開催した団体</h1>
            <v-row>
              <v-col
                v-for="(organization, i) of organizations"
                :key="i"
                cols="12"
                md="4"
              >
                <v-card>
                  <v-img
                    :src="'img/organizations/'+(organization.image)+'.jpg'"
                  >
                  </v-img>
                  <div class="pa-4">
                    <h2 class="text-center">{{ organization.name }}</h2>
                    <p>{{ organization.text }}</p>
                  </div>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </div>
      </v-carousel-item>
      <v-carousel-item
        src="img/slideshow/link-slideshow/slide2.jpg"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto py-16">
          <v-container class="ma-auto white--text">
            <h1 class="text-center">音楽サークル</h1>
            <v-row>
              <v-col
                v-for="(musicCircle, i) of musicCircles"
                :key="i"
                cols="12"
                md="4"
              >
                <v-card>
                  <v-img
                    :src="'img/music-circles/'+(musicCircle.image)+'.jpg'"
                  >
                  </v-img>
                  <div class="pa-4">
                    <h2 class="text-center">{{ musicCircle.name }}</h2>
                    <p>{{ musicCircle.text }}</p>
                  </div>
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
      organizations: [
        {
          name: '北大映画館プロジェクト',
          text: '北大に常設の映画館を作ることを目指している団体。当団体と同じく長年北大元気プロジェクトに採択され続けています。11月に映画館プロジェクトさんが主催する「クラークシアター2015」に「クラークシアターカフェ」を設置させていただきました。',
          image: 'clark-theater'
        },
        {
          name: '犬のM基金',
          text: '「不幸な犬を救いたい」という気持ちで集まった方々の団体。身寄りのない犬たちの保護、里親探し、保護犬の不妊手術、募金集めなどを行っている団体です。活動の輪を広げるためのイベントなども行っており、カフェプロジェクトと共に、わんにゃんかふぇを開催しました。',
          image: 'dog-M-fund'
        },
        {
          name: 'ツキネコ北海道',
          text: '動物管理センターに持ち込まれる猫をできるだけ減らし、殺処分ゼロを目指している団体「猫と人を繋ぐ」ことを目的に、飼い主のいない猫たちに家族を見つけるお手伝いを中心にしています。カフェプロジェクトと共に、わんにゃんかふぇを開催しました。',
          image: 'tsukineko-hokkaido'
        },
      ],
      musicCircles: [
        {
          name: 'アウロラ',
          text: '北大マンドリンサークルのアウロラさん。正式名称は、北海道大学チルコロ・マンドリニスティコ「アウロラ」といいます。1923年から続く歴史の長いサークルです。北大祭カフェや銀杏並木カフェで演奏していただきました。',
          image: 'aurora'
        },
        {
          name: 'ブルーグラス研究会',
          text: 'カントリーミュージックに似た「ブルーグラス」というジャンルの音楽を演奏しているサークルさん。心が弾みます音楽を楽しめます。北大祭カフェや銀杏並木カフェにて、多くのバンドに演奏していただきました。',
          image: 'blueken'
        },
        {
          name: '北海道大学合唱団',
          text: '1915年に創設され、100年の節目を迎えた男声合唱団。札幌を中心に多くの人に 男声合唱を楽しんでもらうことをモットーに日々活動をされています。北大祭カフェなどで美しい歌声を披露してくださいました。',
          image: 'chorus'
        },
        {
          name: '生',
          text: '北大純正アコースティックギターサークル「生」さん。様々なジャンルの音楽を演奏し、観客を盛り上げていただきました。北大マルシェカフェにて、演奏していただきました。',
          image: 'nama'
        },
        {
          name: 'NoSeRA',
          text: '2010年1月に発足した北大のアカペラサークル。150名超のメンバーが所属しています。北大祭カフェやわんにゃんカフェで演奏していただきました。',
          image: 'nosera'
        },
        {
          name: '北海道大学交響楽団',
          text: '北大公認のオーケストラサークルさん。毎年秋にコンサートホール Kitara の大ホールにて定期演奏会を開催されています。北大祭カフェやわんにゃんかふぇで演奏していただきました。',
          image: 'orchestra'
        }
      ]
    }
  },
  head() {
    return {
      title: '外部リンク｜'
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

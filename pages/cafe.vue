<template>
  <div class="fill-height fill-width relative">
    <v-carousel
      height="100%"
      progress
      hide-delimiter-background
    >
      <v-carousel-item
        v-for="(departmentOfCafe, i) of departmentsOfCafe"
        :key="i"
        :src="'img/slideshow/member-slideshow/slide'+(i+1)+'.jpg'"
      >
        <div id="background" class="fill-height fill-width"></div>
        <div id="content" class="align-content-center d-flex fill-height fill-width overflow-auto">
          <v-container class="ma-auto white--text">
            <h1 class="text-center nowrap">{{ departmentOfCafe.departmentName }}</h1>
            <v-row
              justify="center"
            >
              <v-col
                v-for="(member, j) of departmentOfCafe.members"
                id="member__wrapper"
                :key="j"
                cols="6"
                sm="4"
                lg="3"
                class="circle relative"
              >
                <img id="member__image" class="circle fill-width pa-0 object-contain" :src="'img/member/'+member.imageName+'.jpg'" :alt="member.name">
                <div id="member__description" class="absolute ma-auto text-center">
                  <p class="ma-0 text-caption text-sm-body-1">
                    <strong>{{ member.name }}</strong><br>
                    <span v-if="member.position" class="nowrap">【{{ member.position }}】<br></span>
                    <span class="nowrap">{{ member.university }}・{{ member.departmentOfUniversity }}{{ member.grade }}年</span><br>
                    <span class="d-none d-md-inline-block">
                      <strong class="nowrap">好きな飲み物orカフェ</strong><br>
                      <span>{{ member.favorite }}</span><br>
                    </span>
                    <strong class="nowrap">ひとことコメント</strong><br>
                    <span>{{ member.comment }}</span>
                  </p>
                </div>
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
      topSlideshowHeight: 0,
      departmentsOfCafe: [
        {
          departmentName: '代表・副代表',
          members: [
            {
              name: 'そーた',
              imageName: 'sota',
              position: '代表',
              university: '北大',
              departmentOfUniversity: '経済学部',
              grade: 2,
              favorite: '赤の野菜ジュース',
              comment: '4年間で北海道遊び尽くす',
            },
            {
              name: 'いずみん',
              imageName: 'izumin',
              position: '副代表',
              university: '北大',
              departmentOfUniversity: '経済学部',
              grade: 2,
              favorite: '宮越屋珈琲 The Cafe',
              comment: 'カフェイン中毒',
            },
            {
              name: 'ごし',
              imageName: 'goshi',
              position: '副代表',
              university: '北大',
              departmentOfUniversity: '工学部',
              grade: 2,
              favorite: 'カフェオレ',
              comment: '最近は紅茶かも?',
            },
          ],
        },
        {
          departmentName: '渉外部',
          members: [
            {
              name: 'かみちゃん',
              imageName: 'kamichan',
              position: '渉外部長',
              university: '北大',
              departmentOfUniversity: '工学部',
              grade: 2,
              favorite: 'カフェモカ',
              comment: 'このホームページを制作しています',
            },
            {
              name: 'ちひろ',
              imageName: 'chihiro',
              university: '北大',
              departmentOfUniversity: '文学部',
              grade: 4,
              favorite: 'CAVE STORE',
              comment: '最後の1年楽しみ尽くしたい!',
            },
            {
              name: 'ちせ',
              imageName: 'chise',
              university: '北大',
              departmentOfUniversity: '法学部',
              grade: 2,
              favorite: 'ココア',
              comment: 'カフェオレ飲めるようになりました',
            },
            {
              name: 'うっちー',
              imageName: 'ucchi',
              university: '北大',
              departmentOfUniversity: '教育学部',
              grade: 3,
              favorite: '水',
              comment: '熱しやすく冷めやすい器用貧乏です',
            },
            {
              name: 'ゆうき',
              imageName: 'yuki',
              university: '北大',
              departmentOfUniversity: '法学部',
              grade: 2,
              favorite: 'カフェオレ',
              comment: 'お店開拓したいです...!',
            },
            {
              name: 'ごし',
              imageName: 'goshi',
              university: '北大',
              departmentOfUniversity: '工学部',
              grade: 2,
              favorite: 'カフェオレ',
              comment: '最近は紅茶かも?',
            },
          ],
        },
        {
          departmentName: '広報部',
          members: [
            {
              name: 'えりこ',
              imageName: 'eriko',
              position: '広報部長',
              university: '北大',
              departmentOfUniversity: '文学部',
              grade: 2,
              favorite: '佐藤珈琲',
              comment: '好きな飲み物はカフェオレ(甘くないやつ)です',
            },
            {
              name: 'ありさ',
              imageName: 'arisa',
              university: '北大',
              departmentOfUniversity: '経済学部',
              grade: 3,
              favorite: 'メロンソーダ',
              comment: 'TWICEのダヒョンになりたい',
            },
            {
              name: 'いせちゃん',
              imageName: 'isechan',
              university: '北大',
              departmentOfUniversity: '経済学部',
              grade: 3,
              favorite: 'Standard Coffee Lab.',
              comment: '今年も沢山写真撮ります',
            },
            {
              name: 'ちひろ',
              imageName: 'chihiro',
              university: '北大',
              departmentOfUniversity: '文学部',
              grade: 4,
              favorite: 'CAVE STORE',
              comment: '最後1年楽しみ尽くしたい!',
            },
            {
              name: 'みう',
              imageName: 'miu',
              university: '藤女子大',
              departmentOfUniversity: '文学部',
              grade: 3,
              favorite: '紅茶',
              comment: '最近フランスパンにハマりました',
            },
            {
              name: 'ダイキ',
              imageName: 'daiki',
              university: '北大',
              departmentOfUniversity: '農学部',
              grade: 2,
              favorite: '暗めのカフェ',
              comment: '超絶多忙かつ超絶フッ軽になる',
            },
            {
              name: 'そーた',
              imageName: 'sota',
              university: '北大',
              departmentOfUniversity: '経済学部',
              grade: 2,
              favorite: '赤の野菜ジュース',
              comment: '4年間で北海道遊び尽くす',
            },
          ],
        },
        {
          departmentName: 'カフェマネージャー部',
          members: [
            {
              name: 'あつこ',
              imageName: 'atsuko',
              position: 'カフェマネージャー部長',
              university: '北大',
              departmentOfUniversity: '理学部',
              grade: 2,
              favorite: 'ほうじ茶ラテ',
              comment: 'おすすめのカフェ募集してます!',
            },
            {
              name: 'カナ',
              imageName: 'kana',
              university: '藤女子大',
              departmentOfUniversity: '人間生活学部',
              grade: 4,
              favorite: '石田珈琲店',
              comment: '固めのプリンが好みです',
            },
            {
              name: '菜緒',
              imageName: 'nao',
              university: '天使大',
              departmentOfUniversity: '看護栄養学部',
              grade: 2,
              favorite: '紅茶',
              comment: '料理とゲーム好き!',
            },
            {
              name: 'あいり',
              imageName: 'airi',
              university: '北大',
              departmentOfUniversity: '農学部',
              grade: 2,
              favorite: 'Cafe Blue',
              comment: 'おいしいもの巡りが好きです',
            },
            {
              name: 'しゅうや',
              imageName: 'syuya',
              university: '北大',
              departmentOfUniversity: '薬学部',
              grade: 4,
              favorite: 'チャチャドロップ',
              comment: '多趣味人間です',
            },
            {
              name: 'たいこー',
              imageName: 'taiko',
              university: '北大',
              departmentOfUniversity: '医学研究院',
              grade: 1,
              favorite: 'ミルクコーヒー',
              comment: 'カフェプロ3年目です',
            },
            {
              name: 'ひとみん',
              imageName: 'hitomin',
              university: '北大',
              departmentOfUniversity: '工学部',
              grade: 4,
              favorite: '椿サロン',
              comment: '甘いものを食べること、旅行が好きです',
            },
            {
              name: 'ふゆ',
              imageName: 'huyu',
              university: '北大',
              departmentOfUniversity: '理学部',
              grade: 2,
              favorite: 'コーヒー',
              comment: '実家にかわいいウサギがいます',
            },
          ],
        },
        {
          departmentName: '物品管理部',
          members: [
            {
              name: 'ふーか',
              imageName: 'huka',
              position: '物品管理部長',
              university: '藤女子大',
              departmentOfUniversity: '文学部',
              grade: 2,
              favorite: 'C2 Cafe',
              comment: '毎日の楽しみは食パンです',
            },
            {
              name: 'みずか',
              imageName: 'mizuka',
              university: '天使大',
              departmentOfUniversity: '看護栄養学部',
              grade: 2,
              favorite: '紅茶',
              comment: '紅茶好きです!美味しい紅茶教えてくれると喜びます!!',
            },
            {
              name: 'たていしけいた',
              imageName: 'tateishikeita',
              university: '北大',
              departmentOfUniversity: '工学部',
              grade: 2,
              favorite: 'コメダ珈琲館',
              comment: '今年こそピースから卒業したい',
            },
            {
              name: 'いずみん',
              imageName: 'izumin',
              position: '副代表',
              university: '北大',
              departmentOfUniversity: '経済学部',
              grade: 2,
              favorite: '宮越屋珈琲 The Cafe',
              comment: 'カフェイン中毒',
            },
          ],
        },
        {
          departmentName: '会計部',
          members: [
            {
              name: 'あゆか',
              imageName: 'ayuka',
              university: '北大',
              departmentOfUniversity: '工学部',
              grade: 3,
              favorite: 'FAbULOUS',
              comment: '永遠にあらしっく',
            },
            {
              name: 'あかりん',
              imageName: 'akarin',
              university: '北大',
              departmentOfUniversity: '文学部',
              grade: 4,
              favorite: 'ココア',
              comment: '今年もゆるゆる参加します\\( ¨̮ )/',
            },
            {
              name: 'みう',
              imageName: 'miu',
              university: '藤女子大',
              departmentOfUniversity: '文学部',
              grade: 3,
              favorite: '紅茶',
              comment: '最近フランスパンにハマりました',
            },
            {
              name: 'あいり',
              imageName: 'airi',
              university: '北大',
              departmentOfUniversity: '農学部',
              grade: 2,
              favorite: 'Cafe Blue',
              comment: 'おいしいもの巡りが好きです',
            },
          ],
        },
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

#member__image {
  transition: all .3s ease-in-out 0s;
}

#member__wrapper:hover > #member__image {
  filter: brightness(50%);
  transition: all .3s ease-in-out 0s;
}

#member__description {
  left: 50%;
  opacity: 0;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  transition: all .3s ease-in-out 0s;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
}

#member__wrapper:hover > #member__description {
  opacity: 1;
  transition: all .3s ease-in-out 0s;
}
</style>

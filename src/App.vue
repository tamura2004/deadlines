<template lang="pug">
html
  body
    v-app(light)
      v-toolbar(fixed)
        v-toolbar-title(v-text="title")

      main
        v-container(fluid)
          v-layout.mb-4(row v-for="(project,i) in projects",:key="i")
            v-flex(d-flex xs3)
              v-layout(column)
                v-flex(d-flex)
                  v-card.blue.lighten-3
                    v-card-title.py-1: c(v-text="project.number")
                    v-card-text.py-1: h6(v-text="project.name")
                v-flex(d-flex)
                  v-card.blue.lighten-4
                    v-card-title.py-0
                      v-layout(row)
                        v-flex(xs6): c 関東地方
                        v-flex(xs2): c 東京
                        v-flex(xs2): c 埼玉
                        v-flex(xs2): c 群馬
                v-flex(d-flex)
                  v-card.blue.lighten-4
                    v-card-title.py-0
                      v-layout(row)
                        v-flex(xs6): c ★東北地方
                        v-flex(xs2): c 青森
                        v-flex(xs2): c 岩手
                        v-flex(xs2): c 福島
                v-flex(d-flex)
                  v-card.blue.lighten-4
                    v-card-title.py-0
                      v-layout(row)
                        v-flex(xs6): c 九州地方
                        v-flex(xs2): c 福岡
                        v-flex(xs2): c 宮崎
                        v-flex(xs2): c 長崎
            v-flex(d-flex xs1)
              v-layout(column)
                v-flex(d-flex)
                  v-card.green.lighten-3
                    v-card-text.py-0.px-1: c 見積　9/1　レ
                v-flex(d-flex)
                  v-card.green.lighten-3
                    v-card-text.py-0.px-1: c 計画　9/12 レ
                v-flex(d-flex)
                  v-card.orange.lighten-3
                    v-card-text.py-0.px-1: c 設計　9/20
                v-flex(d-flex)
                  v-card
                    v-card-text.py-0.px-1: c 試験
                v-flex(d-flex)
                  v-card
                    v-card-text.py-0.px-1: c 稼働
                v-flex(d-flex)
                  v-card
                    v-card-text.py-0.px-1: c 完了

            v-flex(d-flex xs4): v-card: v-card-text: h6 スケジュール
            v-flex(d-flex xs4): v-card
              v-card-text.py-1: h6 備考
              v-card-text.py-1: c(v-text="project.comments[0].body")
</template>

<script>
  export default {
    data () {
      return {
        steps: ['見積', '計画', '設計', '試験', '稼働', '完了'],
        projects: [
          {
            number: '201709272143-00-a',
            name: 'Vuetifyjsを使ってマテリアルデザインでSPAを構築する',
            members: {
              owner: ['足立', '品川'],
              prime: ['文教', '新宿'],
              ours: ['練馬', '板橋']
            },
            deadlines: {
              estimate: { date: '10/10', done: true },
              plan: { date: '10/15', done: true },
              design: { date: '10/20', done: true },
              build: { date: '10/25', done: false },
              test: { date: '11/10', done: false },
              release: { date: '11/15', done: false },
              close: { date: '11/20', done: false }
            },
            comments: [
              {date: '9/27', body: '口下手な性格のため、会議中に疑問点を聞き出すことが苦手なエンジニアも多いもの。そのため事後的に不明点を確認することを促すためにも上のようなフレーズを仕事で用いるようにするといいでしょう。また、ビジネスパートナーに対して「何なりと（自分に）お申し付けください」と表現したい時のために、“please don’t hesitate to contact me”という、より丁寧な表現も合わせて覚えておきましょう。'}
            ]
          },
          {
            number: '201709272143-00-a',
            name: 'Vuetifyjsを使ってマテリアルデザインでSPAを構築する',
            members: {
              owner: ['足立', '品川'],
              prime: ['文教', '新宿'],
              ours: ['練馬', '板橋']
            },
            deadlines: {
              estimate: { date: '10/10', done: true },
              plan: { date: '10/15', done: true },
              design: { date: '10/20', done: true },
              build: { date: '10/25', done: false },
              test: { date: '11/10', done: false },
              release: { date: '11/15', done: false },
              close: { date: '11/20', done: false }
            },
            comments: [
              {date: '9/27', body: '口下手な性格のため、会議中に疑問点を聞き出すことが苦手なエンジニアも多いもの。そのため事後的に不明点を確認することを促すためにも上のようなフレーズを仕事で用いるようにするといいでしょう。また、ビジネスパートナーに対して「何なりと（自分に）お申し付けください」と表現したい時のために、“please don’t hesitate to contact me”という、より丁寧な表現も合わせて覚えておきましょう。'}
            ]
          },
          {
            number: '201709272143-00-a',
            name: 'Vuetifyjsを使ってマテリアルデザインでSPAを構築する',
            members: {
              owner: ['足立', '品川'],
              prime: ['文教', '新宿'],
              ours: ['練馬', '板橋']
            },
            deadlines: {
              estimate: { date: '10/10', done: true },
              plan: { date: '10/15', done: true },
              design: { date: '10/20', done: true },
              build: { date: '10/25', done: false },
              test: { date: '11/10', done: false },
              release: { date: '11/15', done: false },
              close: { date: '11/20', done: false }
            },
            comments: [
              {date: '9/27', body: '口下手な性格のため、会議中に疑問点を聞き出すことが苦手なエンジニアも多いもの。そのため事後的に不明点を確認することを促すためにも上のようなフレーズを仕事で用いるようにするといいでしょう。また、ビジネスパートナーに対して「何なりと（自分に）お申し付けください」と表現したい時のために、“please don’t hesitate to contact me”という、より丁寧な表現も合わせて覚えておきましょう。'}
            ]
          }
        ],
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'bubble_chart', title: 'Inspire' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Deadlines'
      }
    }
  }
</script>

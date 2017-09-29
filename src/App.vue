<template lang="pug">
html
  body
    v-app(light)
      v-toolbar(fixed)
        v-toolbar-title(v-text="title")

      main
        v-container(fluid)
          v-layout.mb-4.elevation-4(v-for="k in 10",:key="k")
            v-flex(d-flex xs3)
              v-layout(wrap)
                v-flex(d-flex xs12): v-card(dark).blue.darken-4
                  v-card-text.py-1: c {{project.number}}
                  v-card-text.py-1: h6 {{project.name}}
                v-flex(d-flex xs12,v-for="group in project.groups",:key="group.area"): v-card.blue.lighten-4
                  v-layout
                    v-flex(xs5): v-card-text.py-0: c {{group.area}}
                    v-flex(xs2,v-for="member in group.members",:key="member")
                      v-card-text.pa-0: c {{member}}

            v-flex(d-flex xs2)
              v-layout(wrap)
                v-flex(d-flex,xs12,v-for="deadline in project.deadlines",:key="deadline.label"): v-card.px-2
                  v-layout
                    v-flex(xs2)
                      v-icon(v-if="deadline.done").green--text.text--darken-2 done
                      v-icon(v-else).red--text.text--darken-2 warning
                    v-flex(xs6): v-card-text.pa-1: c {{deadline.label}}
                    v-flex(xs4): v-card-text.pa-1: c {{deadline.date}}

            v-flex(d-flex xs4)
              v-card
                v-layout(wrap)
                  v-flex(xs12)
                    v-layout
                      v-flex(v-for="m in 4",:key="m",xs2)
                        p 10/{{m*7}}
                      v-flex(v-for="m in 2",:key="m",xs2)
                        p 11/{{m*7}}
                  v-flex(xs12)
                    v-layout
                      v-flex(offset-xs8 xs4)
                        p.mb-1 ★締切
                    v-layout
                      v-flex(offset-xs2 xs6)
                        p.mb-1 ヒアリング
                        v-progress-linear.my-0(value="80",height="10",info)
                v-flex(xs12)
                  v-layout
                    v-flex(offset-xs5 xs4)
                      p.mb-1 積算
                      v-progress-linear.my-0(value="20",height="10",error)
            v-flex(d-flex xs3): v-card
              v-card-text.py-0: c {{project.comment.date}}
              v-card-text.py-0: c {{project.comment.body}}

</template>

<script>
  export default {
    data () {
      return {
        project: {
          number: '201709272143-00-a',
          name: 'Vuetifyjsを使ってマテリアルデザインでSPAを構築する',
          groups: [
            {
              area: '関東地方',
              members: ['東京', '埼玉', '千葉']
            },
            {
              area: '★東北地方',
              members: ['青森', '岩手', '福島']
            },
            {
              area: '中国地方',
              members: ['広島', '鳥取', '島根']
            }
          ],
          deadlines: [
            {
              done: true,
              label: '受注会議',
              date: '10/10',
              color: 'green'
            },
            {
              done: true,
              label: '開発会議',
              date: '10/15',
              color: 'green'
            },
            {
              done: true,
              label: '設計会議',
              date: '10/20',
              color: 'lime'
            },
            {
              done: false,
              label: '試験会議',
              date: '10/25',
              color: 'lime'
            },
            {
              done: false,
              label: '稼働会議',
              date: '10/30',
              color: 'amber'
            },
            {
              done: false,
              label: '完了会議',
              date: '11/10',
              color: 'deep-orange'
            }
          ],
          comment: {
            date: '9/27',
            body: '口下手な性格のため、会議中に疑問点を聞き出すことが苦手なエンジニアも多いもの。そのため事後的に不明点を確認することを促すためにも上のようなフレーズを仕事で用いるようにするといいでしょう。また、ビジネスパートナーに対して「何なりと（自分に）お申し付けください」と表現したい時の'
          }
        },
        title: 'Deadlines'
      }
    }
  }
</script>

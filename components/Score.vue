<template lang="pug">
  div
    section.score(v-for="score in scores" :key="score.text")
      .columns.if-full.is-mobile.is-multiline.has-text-centered
        .column.is-12-mobile.is-tablet-4
          span.score-game 第 {{ score.text }} 戦
        .column.is-4-mobile.has-text-right
          span.score-number {{ score.marine }}
        .column.is-4-mobile.has-text-centered
          span.score-bar —
        .column.is-4-mobile.has-text-left
          span.score-number {{ score.tigers }}
    section
      .columns.if-full.is-mobile.is-multiline.has-text-centered
        .column.is-12-mobile.is-tablet-4
          span.score-tag 合計
        .column.is-4-mobile.is-tablet-4.has-text-right
          span.score-result ３３
        .column.is-4-mobile.is-tablet-4.has-text-centered
          span.score-result-bar —
        .column.is-4-mobile.is-tablet-4.has-text-left
          span.score-result ４
</template>

<script>
export default {
  name: 'Score',
  computed: {
    scores() {
      return [
        { text: '１', marine: '１０', tigers: '１' },
        { text: '２', marine: '１０', tigers: '０' },
        { text: '３', marine: '１０', tigers: '１' },
        { text: '４', marine: '３', tigers: '２' }
      ]
    }
  }
}
</script>

<style lang="stylus">
.score
  background linear-gradient(-115deg, #7CB7D5, #7CB7D5 70%, #C8B89E 70%) #C8B89E
  margin .5rem 0
  padding .5rem 0
  .columns
  &-game
    color #000
    text-shadow 1px 1px 0 #fff, -1px 1px 0 #fff, 1px -1px 0 #fff, -1px -1px 0 #fff
    font-size 1.5rem
    font-weight bold
  &-number, &-bar
    color #EBE55D
    text-shadow 1px 1px 0 #000, -1px 1px 0 #000, 1px -1px 0 #000, -1px -1px 0 #000
    font-size 1.75rem
    font-weight 900
  &-bar
    font-size 2rem
    line-height: 1.2
    color #fff
  &-tag
    background-color #ED9D2F
    border solid 1px #fff
    padding .5rem
    font-size 2.25rem
    font-weight bold
    color #000
    text-shadow 1px 1px 0 #fff, -1px 1px 0 #fff, 1px -1px 0 #fff, -1px -1px 0 #fff
  &-result,
  &-result-bar
    color #9A4252
    text-shadow 1px 1px 0 #000, -1px 1px 0 #000, 1px -1px 0 #000, -1px -1px 0 #000
    font-size 2.75rem
    font-weight 900
    @media screen and (max-width: 768px)
      font-size 2rem
.columns
  align-items center
</style>

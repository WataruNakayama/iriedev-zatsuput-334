<template lang="pug">
  section.hero.is-info.is-fullheight
    section.fog
      figure.absolute-bg
      .fog__container
        .fog__img.fog__img--first
        .fog__img.fog__img--second
    .hero-body
      .container
        .column.is-8.is-offset-2
          .card
            .card-content
              .content
                .columns.if-full.is-mobile.is-multiline.has-text-centered
                  .column.is-tablet-2.is-hidden-mobile
                  .column.is-tablet-2.is-hidden-mobile
                  .column.is-4-mobile.is-tablet-2.logo-marines
                    img.image(src="/mariners-logo.png")
                  .column.is-4-mobile.is-tablet-2.has-text-right
                  .column.is-4-mobile.is-tablet-2.logo-tigers.has-text-centered
                    img.image(src="/tigers-70th-logo.png")
                  .column.is-2-tablet.is-hidden-mobile
                score
</template>

<script>
import Navbar from '~/components/Navbar'
import Score from '~/components/Score'
export default {
  components: {
    Navbar,
    Score
  },
  data() {
    return {
      is_button_disabled: false
    }
  },
  mounted() {
    const audio = new Audio(require('../static/chin.mp3'))
    audio.play()
  }
}
</script>

<style lang="stylus">
body
  overflow-x hidden
.hero
  &.is-info
    background linear-gradient(
      rgba(0, 0, 0, 0.5),
      rgba(0, 0, 0, 0.5)
    ), url('/zozo-marine-stadium.jpg') no-repeat center center fixed
    -webkit-background-size cover
    -moz-background-size cover
    -o-background-size cover
    background-size cover
  .subtitle
    padding 3rem 0
    line-height 1.5
.fog
  position absolute
  top 0
  left 0
  z-index 0
  height 100%
  width 100%
  &__container
    position absolute
    height 100%
    width 100%
    overflow hidden
  &__img
    position absolute
    height 100vh
    width 300vw
    &--first
      background url('https://res.cloudinary.com/dkr52htco/image/upload/v1536173269/fog-1.png') repeat-x
      background-size contain
      background-position center
      animation marquee 50s linear infinite
    &--second
      background url('https://res.cloudinary.com/dkr52htco/image/upload/v1536173269/fog-2.png') repeat-x
      background-size contain
      background-position center
      animation marquee 30s linear infinite
@keyframes marquee
  0%
    transform translate3d(0, 0, 0)
  100%
    transform translate3d(-200vw, 0, 0)
.logo
  &-marines
    padding-left 0
  &-tigers
    position relative
    margin-right -20px
    padding-right 0
    margin-bottom -5px
</style>

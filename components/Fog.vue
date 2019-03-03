<template lang="pug">
  section.fog
    figure.absolute-bg(style="background-image: url('/zozo-marine-stadium.jpg');")
    .fog__container
      .fog__img.fog__img--first
      .fog__img.fog__img--second
    p Hello!
</template>

<script>
export default {
  name: 'Fog'
}
</script>

<style lang="stylus">
figure
  margin 0
.absolute-bg
  position absolute
  top 0
  left 0
  z-index 0
  height 100%
  width 100%
  background-position 50%
  background-repeat no-repeat
  background-size cover
  overflow hidden
.fog
  position relative
  height 100vh
  width 100%
  background-color #000
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
</style>

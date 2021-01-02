<template lang="pug">
  .homeContainer
    .homeText
      p.header3 Lenildo Luan
      p.bodyText Developer & UX/UI Designer

    img(src="~static/images/logo.png", class="logoImage")
</template>

<script>
export default {}
</script>

<style lang="sass">
.homeContainer
  width: 100%
  height: 100%
  position: relative

.logoImage
  position: absolute
  top: 50%
  left: 50%
  transform: translate(-50%, -50%)
  width: 325px
  height: 325px

.homeText
  height: 100px
  position: absolute
  top: 50%
  margin-left: 70px
  margin-top: -50px

@media (max-width: 990px)
  .homeContainer
    min-height: 100vh
  .homeText
    width: 100%
    top: 85%
    left: 50%
    margin-left: 0px
    transform: translate(-50%, -0%)
    display: flex
    flex-direction: column
    align-items: center
</style>

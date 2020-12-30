<template lang="pug">
  div.homeContainer
    div.homeText
      p.header3 Lenildo Luan
      p.bodyText Developer & UX/UI Designer

    img(src="~static/images/logo.png", width="325px", height="325px", class="logoImage")
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
  margin-left: -162px
  margin-top: -162px

.homeText
  height: 100px
  position: absolute
  top: 50%
  left: 10%
  margin-top: -50px

@media (max-width: 776px)
  .homeContainer
    position: absolute
</style>

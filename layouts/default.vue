<template lang="pug">
.containerFluid
  .containerFixed
    NuxtLink.bodyText(
      v-for='link in links',
      :key='link.id',
      :to='link.to',
      :class='link.class'
    ) {{ link.name }}
    Nuxt
  div(v-for='line in lines', :class='line.class')
</template>

<script>
export default {
  data: () => {
    return {
      lines: [
        { class: 'l1' },
        { class: 'l2' },
        { class: 'l3' },
        { class: 'l4' },
        { class: 'l5' },
      ],
      links: [
        {
          id: 0,
          to: '/about',
          name: 'sobre mim',
          class: 'link1',
        },
        {
          id: 1,
          to: '/contact',
          name: 'fale comigo',
          class: 'link2',
        },
        {
          id: 2,
          to: '/services',
          name: 'serviços',
          class: 'link3',
        },
        {
          id: 3,
          to: '/',
          name: 'home',
          class: 'link4',
        },
      ],
    }
  },
}
</script>

<style lang="sass">
a
  text-decoration: none
  color: #101010
  z-index: 20

.containerFluid
  width: 100%
  height: 100vh
  display: flex
  align-items: center
  justify-content: center

.containerFixed
  width: 1241px
  max-width: 1400px
  height: 90%
  position: relative
  z-index: 10

.link1
  position: absolute
  top: 0
  left: 0

.link2
  position: absolute
  top: 0
  right: 0

.link3
  position: absolute
  bottom: 0
  left: 0

.link4
  position: absolute
  bottom: 0
  right: 0

@mixin line($distance)
  height: 100vh
  border-left: solid #000 1px
  position: absolute
  opacity: 0.1
  left: $distance
  z-index: 0

.l1
  @include line(15%)

.l2
  @include line(32.5%)

.l3
  @include line(50%)

.l4
  @include line(67.5%)

.l5
  @include line(85%)

@media (max-width: 776px)
  .l1
    display: none
  .l2
     @include line(25%)
  .l4
     @include line(75%)
  .l5
    display: none
  .link1
    position: relative
  .link2
    position: relative
  .link3
    position: relative
  .link4
    position: relative
  .containerFixed
    display: flex
    flex-direction: row
    justify-content: space-evenly
</style>

<template lang="pug">
div.containerFluid
  div.containerFixed
    NuxtLink(v-for='link in links', :key='link.id', :to='link.to', :class='link.class').bodyText {{link.name}}
    Nuxt
</template>

<script>
export default {
  data: () => {
    return {
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

.containerFluid
  width: 100%
  height: 100vh
  display: flex
  align-items: center
  justify-content: center

.containerFixed
  width: 1241px
  min-width: 990px
  height: 90%
  position: relative

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
</style>

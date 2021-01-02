<template lang="pug">
.containerFluid
  //- BACKGROUND
  .white
    .squares
      .square(v-for='square in squaresQtd')

  div(v-for='line in lines', :class='line.class')

  //- NAVEGATION
  input#menu-hamburguer(
    v-model='showMenu',
    type='checkbox',
    v-on:click='showMenu = !showMenu'
  )
  
  label(for='menu-hamburguer')
    .menuNav
      span.hamburguer

  transition(name='fade')
    ul.menuList(v-show='showMenu')
      li(
        v-for='item in items',
        :key='item.name',
        v-on:click='showMenu = !showMenu'
      )
        NuxtLink.header3.bg1menu.menuLink(:to='item.to') {{ item.name }}

  //- CONTENT
  .containerFixed
    Nuxt(keep-alive)
</template>

<script>
export default {
  data: () => {
    return {
      squaresQtd: 9,
      lines: [
        { class: 'line left50' },
        { class: 'line left30' },
        { class: 'line left10' },
        { class: 'line left70' },
        { class: 'line left90' },
      ],
      showMenu: false,
      checked: false,
      items: [
        { name: 'Home', to: '/' },
        { name: 'Sobre', to: '/about' },
        { name: 'Serviços', to: '/services' },
        // { name: 'Portfolio' },
        // { name: 'Laboratory', to: '/laboratory' },
        { name: 'Contato', to: '/contact' },
      ],
    }
  },
}
</script>

<style lang="sass">
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

@media (max-width: 990px)
  .containerFluid
    height: auto
    min-height: 100vh
  .containerFixed
    max-width: 100vw
    height: auto
    min-height: 100vh

/* BACKGROUND  */
.white
  height: 100vh
  width: 100vw
  position: fixed

.squares
  height: 100%
  display: flex
  justify-content: space-around
  overflow: hidden
  opacity: 0.5

.square
  animation: squares 9.5s linear infinite
  align-self: flex-end
  width: 1em
  height: 1em
  transform: translateY(100%)
  background: #ebebeb

  &:nth-child(2)
    height: 1.5em
    width: 3em
    animation-delay: 1s
    animation-duration: 17s
    -webkit-filter: blur(5px)

  &:nth-child(3)
    height: 2em
    width: 1em
    animation-delay: 1.5s
    animation-duration: 8s
    -webkit-filter: blur()

  &:nth-child(4)
    height: 1em
    width: 1.5em
    animation-delay: 0.5s
    -webkit-filter: blur(3px)
    animation-duration: 13s

  &:nth-child(5)
    height: 1.25em
    width: 2em
    animation-delay: 4s
    -webkit-filter: blur(2px)
    animation-duration: 11s

  &:nth-child(6)
    height: 2.5em
    width: 2em
    animation-delay: 2s
    -webkit-filter: blur(1px)
    animation-duration: 9s

  &:nth-child(7)
    height: 5em
    width: 2em
    -webkit-filter: blur(2.5px)
    animation-duration: 12s

  &:nth-child(8)
    height: 1em
    width: 3em
    animation-delay: 5s
    -webkit-filter: blur(6px)
    animation-duration: 18s

  &:nth-child(9)
    height: 1.5em
    width: 2em
    -webkit-filter: blur(0.5px)
    animation-duration: 9s

  &:nth-child(9)
    height: 3em
    width: 2.4em
    animation-delay: 6s
    -webkit-filter: blur(0.5px)
    animation-duration: 12s

@keyframes squares
  from
    transform: translateY(100%) rotate(-50deg)

  to
    transform: translateY(calc(-100vh + -100%)) rotate(20deg)

.line
  width: 1px
  height: 100vh
  position: fixed
  top: 0
  overflow: hidden
  background: #2f2f2f
  opacity: 0.1

.left50
  left: 50%

.left30
  left: 30%

.left10
  left: 10%

.left90
  left: 90%

.left70
  left: 70%

/* TRANSITIONS */
.fade-enter-active
  transition: opacity .5s .2s

.fade-leave-active
  transition: opacity .5s

.fade-enter, .fade-leave-to
  opacity: 0

/* NAVEGATION */
input
  display: none

li
  margin-bottom: 10px

.menuList
  list-style-type: none
  position: fixed
  top: 50%
  left: 50%
  transform: translate(-50%, -50%)
  z-index: 2000
  cursor: none

.menuLink
  color: #fff !important
  text-decoration: none
  padding: 0 20px 0 20px
  transition: .3s ease-in-out
  border-radius: 5px

  &:hover
    background-size: 100% 100%
    cursor: pointer

.menuNav
  background: #fff
  border-radius: 50%
  height: 50px
  width: 50px
  position: fixed
  bottom: 25px
  right: 25px
  z-index: 1000
  cursor: pointer
  box-shadow: 0 0 0 0 #2F2F2F, 0 0 0 0 #2F2F2F
  transition: .5s ease-in-out !important

  &:hover
    background: #2F2F2F

    .hamburguer
      background: #fff

      &:before
        background: #fff

      &:after
        background: #fff

input:checked ~ label .menuNav
  z-index: 2000
  box-shadow: 0 0 0 225vw #2F2F2F, 0 0 0 225vw #2F2F2F

.hamburguer
  position: relative
  display: block
  background: #2F2F2F
  width: 30px
  height: 1px
  top: 25px
  left: 11px
  transition: .5s ease-in-out

  &:before,
  &:after
    background: #2F2F2F
    content: ''
    display: block
    width: 50%
    height: 100%
    position: absolute
    transition: .5s ease-in-out

  &:before
    top: -10px
    right: 0

  &:after
    bottom: -10px

input:checked ~ label .hamburguer
  transform: rotate(45deg)

input:checked ~ label .hamburguer:before
  transform: rotate(90deg)
  top: 0

input:checked ~ label .hamburguer:after
  transform: rotate(90deg)
  bottom: 0

.bg1menu
  background: linear-gradient(to left, #4facfe 0%, #00f2fe 100%)
  background-position: 0% 100%
  background-repeat: repeat-y
  background-size: 0px 100%

.bg2menu
  background: linear-gradient(to left, #43e97b , #38f9d7)
  background-position: 0% 100%
  background-repeat: repeat-y
  background-size: 0px 100%

.bg3menu
  background: linear-gradient(to left, #fa709a , #fde039)
  background-position: 0% 100%
  background-repeat: repeat-y
  background-size: 0px 100%

.bg4menu
  background: linear-gradient(to left, #f83600 , #f9d423)
  background-position: 0% 100%
  background-repeat: repeat-y
  background-size: 0px 100%

.bg5menu
  background: linear-gradient(to left, #fa709a , #fde039)
  background-position: 0% 100%
  background-repeat: repeat-y
  background-size: 0px 100%
</style>

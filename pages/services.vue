<template lang="pug">
.servicesContainer
  .servicesSection1
    p.header3 Desenvolvimento Web/Mobile
    p.bodyText.
       Desenvolvo projetos que causem impacto. Desde um aplicativo que muda a forma como uma universidade executa um evento até 
       websites e incríveis. Adoro estudar e trabalhar com desenvolvimento, por isso estou sempre me aperfeiçoando e pondo em prática
       novos conhecimentos.
  .servicesSection2
    p.header3 UX/UI Design
    p.bodyText.
      Crio experiências de usuário que resolvam problemas reais, baseado em dados e pesquisas com usuários. A partir delas,
      monto interfaces criativas que conversem com sua marca. Antes de ter um produto é necessário ter um projeto, por isso sempre busco
      me aprimorar sobre interface e experiência de usuário.
  NuxtLink.servicesButton.bodyText(to="/contact") Fale comigo
</template>

<script>
export default {
  head() {
    return {
      title: 'Lenildo Luan - Serviços',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Desenvolvo projetos que causem impacto e experiências de usuário que resolvam problemas reais.',
        },
      ],
    }
  },
}
</script>

<style lang="sass">
.servicesContainer
  width: 100%
  height: 100%
  display: flex
  flex-direction: column
  justify-content: center

.servicesContainer
  .header3
    margin-bottom: 14px

.servicesSection1
  margin-bottom: 35px
  width: 840px
  margin-left: 70px

.servicesSection2
  margin-bottom: 35px
  width: 840px
  margin-left: 70px

.servicesButton
  margin-left: 70px
  color: #ffffff
  text-decoration: none
  background: #060606
  height: 48px
  width: 140px
  border-radius: 10px
  display: flex
  align-items: center
  justify-content: center

@media (max-width: 990px)
  .servicesContainer
    min-height: 100vh

  .servicesSection1
    margin-left: 5vw
    width: 90vw

  .servicesSection2
    margin-left: 5vw
    width: 90vw

  .servicesButton
    margin-left: 5vw
</style>

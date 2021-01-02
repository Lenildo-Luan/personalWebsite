<template lang="pug">
.aboutContainer
  .aboutSection1
    p.header3 Prazer, Luan
    p.bodyText.
      Sou um estudante de Engenharia de Computação na UFPB, onde busco me especializar em pesquisa operacional, área da computação
      utilizada por grandes empresas como Amazon para tomar melhores decisões. 
      <br><br>
      Tentando fazer alguma diferença no mundo, fui um dos responsáveis pela abertura do capítulo de robótica e automação do IEEE UFPB 
      criando uma comunidade local de robótica, cofundei a Bravadus para ajudar jovens startups a causarem impacto no mundo e crio conteúdo
      sobre web e computação no meu instagram. 
      <br><br>
    .sigaSubsection
      p.caption Acompanhe minha jornada:
      a.bodyTitle(v-for='link in links', :href='link.to', target='_blank') {{ link.name }}
    //- NuxtLink.aboutButton.bodyText(to="/contact") Fale comigo

  .aboutSection2
    img(src='~static/images/eu.png', width='80%')
</template>

<script>
export default {
  data: () => {
    return {
      links: [
        { name: 'Instagram', to: 'https://www.instagram.com/lenildoluan/' },
        { name: 'Github', to: 'https://github.com/Lenildo-Luan' },
        { name: 'Dribbble', to: 'https://dribbble.com/lluan_' },
        { name: 'Behance', to: 'https://www.behance.net/lenildolua3ae1' },
      ],
    }
  },
  head() {
    return {
      title: 'Lenildo Luan - Sobre mim',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'Sou um estudante de Engenharia de Computação na UFPB, onde busco me especializar em pesquisa operacional, área da computação utilizada por grandes empresas como Amazon para tomar melhores decisões.',
        },
      ],
    }
  },
}
</script>

<style lang="sass">
.aboutContainer
  width: 100%
  height: 100%
  display: flex
  flex-direction: row
  align-items: center
  justify-content: space-space-evenly

.aboutSection1
  width: 50%
  margin-left: 70px

  .header3
    margin-bottom: 14px
  .bodyText
    margin-bottom: 14px

.aboutSection2
  width: 50%
  display: flex
  align-items: center
  justify-content: center

.aboutButton
  color: #ffffff
  text-decoration: none
  background: #060606
  height: 48px
  width: 140px
  border-radius: 10px
  display: flex
  align-items: center
  justify-content: center

.sigaSubsection
  a
    font-family: Barlow-Regular
    margin-right: 14px
    text-decoration: none
    color: #060606

@media (max-width: 990px)
  .aboutContainer
    flex-direction: column-reverse
    height: auto

  .aboutSection1
    width: 90vw
    margin-left: 0
    margin-bottom: 5vh

  .aboutSection2
    width: 100%
    margin-bottom: 5vh
    margin-top: 5vh
</style>

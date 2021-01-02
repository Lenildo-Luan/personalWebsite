<template lang="pug">
.contactContainer
  .containerSection1
    p.header3 Vamos fazer algo incrível?
    p.bodyText Não tenha vergonha, entre em contato e vamos conversar :D
  .containerSection2
    .contactSubsection
      p.caption Contato:
      p.bodyTitle lenildoluan@gmail.com
    .sigaSubsection
      p.caption Me siga:
      a.bodyTitle(v-for='link in links', :href="link.to", target="_blank") {{ link.name }}
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
      title: 'Lenildo Luan - Contato',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Não tenha vergonha, entre em contato e vamos conversar :D',
        },
      ],
    }
  },
}
</script>

<style lang="sass">
.contactContainer
  width: 100%
  height: 100%
  display: flex
  flex-direction: column
  justify-content: center

.containerSection1
  margin-bottom: 70px
  margin-left: 70px

.containerSection2
  margin-left: 70px
  display: flex

  .bodyTitle
    font-family: Barlow-Regular

.contactSubsection
  margin-right: 140px

.sigaSubsection
    a
      margin-right: 14px
      text-decoration: none
      color: #060606

@media (max-width: 990px)
  .contactContainer
    min-height: 100vh

  .containerSection1
    margin-left: 5vw
    width: 90vw

  .containerSection2
    margin-left: 5vw
    width: 90vw
    flex-direction: column

  .contactSubsection
    margin-bottom: 14px
</style>

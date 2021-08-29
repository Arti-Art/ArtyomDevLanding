<template>
  <div class="container">
    <main>
      <SectionAbout />
      <BlackBar />
      <SectionSkills />
      <SectionPortfolio />
    </main>
  </div>
</template>

<script>
import SectionAbout from '~/components/SectionAbout.vue'
import BlackBar from '~/components/BlackBar.vue'

export default {
  components: {
    SectionAbout,
    BlackBar
  },
}
</script>

<style scoped lang="scss">

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}

</style>

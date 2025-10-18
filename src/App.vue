<template>
  <div>
    <!-- Navbar -->
    <Navbar :activeTab="activeTab" @change-tab="changeTab" />

    <!-- Hero -->
    <Hero @change-tab="changeTab" />

    <!-- Conteúdo -->
    <section class="content">
      <!-- Quem Somos -->
      <div v-show="activeTab === 'quem-somos'">
        <WhoWeAre />
      </div>

      <!-- Nossa Política -->
      <div v-show="activeTab === 'politica'">
        <Policy />
      </div>

      <!-- Nosso Dilema -->
      <div v-show="activeTab === 'dilema'">
        <Dilemma />
      </div>

      <!-- Onde Embarcamos -->
      <div v-show="activeTab === 'onde-embarcamos'">
        <WhereWeEmbark />
      </div>

      <!-- Trabalhe Conosco -->
      <div v-show="activeTab === 'trabalhe-conosco'">
        <WorkWithUs :open="activeTab === 'trabalhe-conosco'" />
      </div>
    </section>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import WhoWeAre from './components/WhoWeAre.vue'
import Policy from './components/Policy.vue'
import Dilemma from './components/Dilemma.vue'
import WhereWeEmbark from './components/WhereWeEmbark.vue'
import WorkWithUs from './components/WorkWithUs.vue'

export default {
  name: "App",
  components: { Navbar, Hero, WhoWeAre, Policy, Dilemma, WhereWeEmbark, WorkWithUs },
  data() {
    return {
      activeTab: 'quem-somos'
    }
  },
  methods: {
    changeTab(tabName) {
      this.activeTab = tabName

      // Scroll suave apenas para a aba Trabalhe Conosco
      if (tabName === 'trabalhe-conosco') {
        this.$nextTick(() => {
          const element = document.getElementById('work-with-us')
          if (element) {
            element.scrollIntoView({ behavior: 'smooth' })
          }
        })
      }
    }
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background: #e0f7ff;
}
.content {
  padding: 40px 20px;
  max-width: 1200px;
  margin: auto;
}
</style>

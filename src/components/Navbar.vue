<template>
  <nav class="navbar">
    <div class="logo-container">
      <img src="/mare-alta-logo.png" alt="MaréAlta" />
    </div>
    <ul class="nav-links">
      <li :class="{ active: activeTab === 'quem-somos' }" @click="changeTab('quem-somos')">Quem Somos</li>
      <li :class="{ active: activeTab === 'politica' }" @click="changeTab('politica')">Nossa Política</li>
      <li :class="{ active: activeTab === 'dilema' }" @click="changeTab('dilema')">Nosso Dilema</li>
      <li :class="{ active: activeTab === 'onde-embarcamos' }" @click="changeTab('onde-embarcamos')">Onde Embarcamos</li>
      <li :class="{ active: activeTab === 'trabalhe-conosco' }" @click="changeTab('trabalhe-conosco')">Trabalhe Conosco</li>
    </ul>
    <button class="cta" @click="changeTab('trabalhe-conosco')">Explore nossas vagas</button>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    activeTab: {
      type: String,
      required: true
    }
  },
  methods: {
    changeTab(tab) {
      this.$emit('change-tab', tab)
    }
  }
}
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 40px;
  background: linear-gradient(to right, #00c6ff, #0072ff);
  font-family: 'Poppins', sans-serif;
  color: white;
  position: sticky;
  top: 0;
  z-index: 1000;
  height: 100px;        /* altura fixa da navbar */
  overflow: hidden;     /* impede que a logo saia da barra */
}

.logo-container {
  height: 100%;
  display: flex;
  align-items: center;
}

.logo-container img {
  height: 200%;           /* ocupa 85% da altura da navbar */
  animation: float 4s ease-in-out infinite;
  transition: transform 0.3s ease;
}

/* Flutuação suave, limitada para não sair da barra */
@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-5px);
  }
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 30px;
  align-items: center;
}

.nav-links li {
  cursor: pointer;
  font-weight: 500;
  transition: 0.3s;
}

.nav-links li:hover,
.nav-links li.active {
  text-decoration: underline;
}

.cta {
  background-color: #ffdd57;
  color: #0072ff;
  padding: 10px 20px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
  transition: 0.3s;
}

.cta:hover {
  background-color: #ffd700;
}

/* Responsividade */
@media (max-width: 768px) {
  .logo-container img {
    height: 70%;
  }
}

@media (max-width: 480px) {
  .navbar {
    flex-direction: column;
    gap: 10px;
    height: auto;
    padding: 10px 20px;
  }

  .logo-container img {
    height: 60%;
  }

  .nav-links {
    flex-direction: column;
    gap: 15px;
    align-items: center;
  }
}
</style>

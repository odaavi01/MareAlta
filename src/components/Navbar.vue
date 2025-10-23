  <template>
    <nav class="navbar">
      <div class="logo">
        <!-- Logo usando import -->
        <img :src="logo" alt="MaréAlta" />
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
  import logoImg from '../assets/mare-alta-logo.png';

  export default {
    name: 'Navbar',
    props: {
      activeTab: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        logo: logoImg
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
    padding: 20px 40px;
    background: linear-gradient(to right, #00c6ff, #0072ff);
    color: white;
    font-family: 'Poppins', sans-serif;
    position: sticky;
    top: 0;
    z-index: 1000;
  }

  .logo img {
    height: 50px;
  }

  .nav-links {
    display: flex;
    list-style: none;
    gap: 30px;
  }

  .nav-links li {
    cursor: pointer;
    transition: 0.3s;
    font-weight: 500;
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
  </style>

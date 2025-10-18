<template>
  <section class="ports-section">
    <h2>Onde Embarcamos</h2>
    <p class="intro">
      Conheça os principais portos onde nossos cruzeiros iniciam suas viagens.  
      Escolha o ponto de partida ideal e embarque nessa experiência inesquecível!
    </p>

    <div class="port-list">
      <div
        v-for="(port, index) in ports"
        :key="index"
        class="port-card"
        @click="selectPort(index)"
      >
        <img :src="port.image" :alt="port.name" />
        <h3>{{ port.name }}</h3>
        <p>{{ port.description }}</p>
      </div>
    </div>

    <transition name="fade">
      <div v-if="selectedPort !== null" class="map-container">
        <h3>📍 {{ ports[selectedPort].name }} - {{ ports[selectedPort].state }}</h3>
    <iframe
  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3671569.908480804!2d-47.83484796792655!3d-21.78187824532892!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce5b92b37f2d25%3A0xdee9e0ad8f30c347!2sPorto%20de%20Santos!5e0!3m2!1spt-BR!2sbr!4v1728888888888!5m2!1spt-BR!2sbr"
  width="100%"
  height="400"
  style="border:0; border-radius: 10px;"
  allowfullscreen=""
  loading="lazy"
></iframe>

        <button @click="selectedPort = null" class="close-map">Fechar mapa</button>
      </div>
    </transition>
  </section>
</template>

<script>
export default {
  name: "WhereWeEmbark",
  data() {
    return {
      selectedPort: null,
      ports: [
        {
          name: "Porto de Santos",
          state: "São Paulo (SP)",
          description: "Maior porto da América Latina e principal ponto de embarque dos cruzeiros no Brasil.",
          image: "https://upload.wikimedia.org/wikipedia/commons/1/17/Porto_de_Santos_2016.jpg",
          mapUrl: "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3674.8580284843573!2d-46.32124742386461!3d-23.94169227790751!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce1c7d2b2c8f69%3A0x4a258ae5e83a43e4!2sPorto%20de%20Santos!5e0!3m2!1spt-BR!2sbr!4v1697022080000!5m2!1spt-BR!2sbr"
        },
        {
          name: "Porto do Rio de Janeiro",
          state: "Rio de Janeiro (RJ)",
          description: "Com vista para o Pão de Açúcar, o porto carioca é um dos mais belos pontos de partida.",
          image: "https://upload.wikimedia.org/wikipedia/commons/8/8d/Porto_do_Rio_de_Janeiro_-_RJ.JPG",
          mapUrl: "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3675.625164964437!2d-43.17437062386514!3d-22.895399477911395!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x997f62dbf2b8b3%3A0xb6bfb75cb3401a36!2sPorto%20do%20Rio%20de%20Janeiro!5e0!3m2!1spt-BR!2sbr!4v1697022200000!5m2!1spt-BR!2sbr"
        },
        {
          name: "Porto de Salvador",
          state: "Bahia (BA)",
          description: "Localizado na Baía de Todos os Santos, é parada obrigatória para quem busca sol e cultura.",
          image: "https://upload.wikimedia.org/wikipedia/commons/3/38/Porto_de_Salvador_-_Bahia.jpg",
          mapUrl: "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3876.457660053097!2d-38.5089345239974!3d-12.971836990857373!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x71604b038a5ab49%3A0x80cefbac81c0e10b!2sPorto%20de%20Salvador!5e0!3m2!1spt-BR!2sbr!4v1697022300000!5m2!1spt-BR!2sbr"
        },
        {
          name: "Porto de Recife",
          state: "Pernambuco (PE)",
          description: "Ponto estratégico para cruzeiros pelo Nordeste, com belas paisagens e história rica.",
          image: "https://upload.wikimedia.org/wikipedia/commons/d/d1/Porto_do_Recife_PE.jpg",
          mapUrl: "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3948.2981516566823!2d-34.871899423937176!3d-8.061210994188256!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x7ab18a24d9ad9e3%3A0x5f6d1a8fa1df4b91!2sPorto%20do%20Recife!5e0!3m2!1spt-BR!2sbr!4v1697022400000!5m2!1spt-BR!2sbr"
        },
        {
          name: "Porto de Itajaí",
          state: "Santa Catarina (SC)",
          description: "Um dos portos mais modernos do Brasil, com cruzeiros pelo Sul e Mercosul.",
          image: "https://upload.wikimedia.org/wikipedia/commons/7/77/Porto_de_Itajai.jpg",
          mapUrl: "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3530.864322887959!2d-48.66531592373665!3d-26.90797177671658!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94d8b73e4bfb9939%3A0xd31675a11efbe48b!2sPorto%20de%20Itaja%C3%AD!5e0!3m2!1spt-BR!2sbr!4v1697022500000!5m2!1spt-BR!2sbr"
        }
      ]
    };
  },
  methods: {
    selectPort(index) {
      this.selectedPort = index;
    }
  }
};
</script>

<style scoped>
.ports-section {
  padding: 60px 20px;
  text-align: center;
  background: linear-gradient(to bottom, #e0f7fa, #ffffff);
  color: #003366;
}

.intro {
  max-width: 700px;
  margin: 0 auto 40px;
  font-size: 1.1rem;
  color: #004d66;
}

.port-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
  gap: 25px;
  justify-content: center;
}

.port-card {
  background: white;
  border-radius: 16px;
  box-shadow: 0 4px 15px rgba(0, 51, 102, 0.1);
  padding: 15px;
  transition: 0.3s;
  cursor: pointer;
}

.port-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 6px 20px rgba(0, 51, 102, 0.15);
}

.port-card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 12px;
  margin-bottom: 10px;
}

.map-container {
  margin-top: 50px;
  text-align: center;
  animation: fadeIn 0.4s ease-in;
}

.close-map {
  background: #0077b6;
  color: white;
  border: none;
  padding: 10px 16px;
  border-radius: 8px;
  margin-top: 10px;
  cursor: pointer;
  transition: 0.3s;
}
.close-map:hover {
  background: #005f8f;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.4s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(15px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>

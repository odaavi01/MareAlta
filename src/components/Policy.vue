<template>
  <section class="policy">
    <div class="container">
      <h1>Nossa Política</h1>
      <p class="intro">
        Na <strong>MaréAlta Cruises</strong>, seguimos padrões de sustentabilidade, segurança e conforto para garantir experiências únicas a bordo.
      </p>

      <div class="cards">
        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/shield.png" alt="Segurança" />

          <h2>Segurança em Primeiro Lugar</h2>
          <p>
            Treinamentos constantes da equipe e protocolos rigorosos garantem viagens seguras para todos.
          </p>
        </div>

        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/earth-planet.png" alt="Sustentabilidade" />
          <h2>Sustentabilidade</h2>
          <p>
            Nossos navios utilizam tecnologias verdes e programas de reciclagem a bordo.
          </p>
        </div>

        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/compass.png" alt="Exploração" />
          <h2>Exploração Consciente</h2>
          <p>
            Roteiros planejados com respeito à cultura local e aos ecossistemas visitados.
          </p>
        </div>

        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/customer-support.png" alt="Atendimento" />
          <h2>Atendimento Premium</h2>
          <p>
            Atendimento humanizado e personalizado, fazendo você se sentir em casa no mar.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Policy",
};
</script>

<style scoped>
.policy {
  background: linear-gradient(to bottom, #d0f0fd, #ffffff);
  padding: 60px 20px;
  font-family: 'Poppins', sans-serif;
  color: #0c4a6e;
}

.container {
  max-width: 1100px;
  margin: auto;
}

h1 {
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 20px;
}

.intro {
  text-align: center;
  font-size: 1.2rem;
  margin-bottom: 50px;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
}

.card {
  background: #ffffffcc;
  padding: 20px;
  border-radius: 15px;
  flex: 1 1 250px;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0,0,0,0.1);
  transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.2);
}

.card img {
  width: 60px;
  height: 60px;
  margin-bottom: 15px;
}

.card h2 {
  font-size: 1.3rem;
  margin-bottom: 10px;
}

.card p {
  font-size: 0.95rem;
  line-height: 1.5;
}
</style>

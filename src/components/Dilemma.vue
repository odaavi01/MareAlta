<template>
  <section class="dilemma">
    <div class="container">
      <h1>Nosso Dilema</h1>
      <p class="intro">
        Explorar os 7 mares mantendo conforto, segurança e sustentabilidade é o desafio que nos move todos os dias.
      </p>

      <div class="cards">
        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/compass.png" alt="Exploração" />
          <h2>Exploração</h2>
          <p>Ampliar rotas e experiências únicas pelo mundo, sem comprometer o conforto dos passageiros.</p>
        </div>

        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/ship.png" alt="Conforto" />
          <h2>Conforto</h2>
          <p>Garantir viagens agradáveis, com acomodações modernas, serviços personalizados e entretenimento a bordo.</p>
        </div>

        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/water.png" alt="Sustentabilidade" />
          <h2>Sustentabilidade</h2>
          <p>Operar de forma eco-friendly, preservando o meio ambiente e respeitando os oceanos que exploramos.</p>
        </div>

        <div class="card">
          <img src="https://img.icons8.com/ios-filled/100/0c4a6e/handshake.png" alt="Segurança" />
          <h2>Segurança</h2>
          <p>Manter protocolos de segurança rigorosos para passageiros e tripulação em todas as viagens.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Dilemma",
};
</script>

<style scoped>
.dilemma {
  background: linear-gradient(to bottom, #e0f7ff, #d0f0ff);
  padding: 60px 20px;
  font-family: 'Poppins', sans-serif;
  color: #1a202c;
}

.container {
  max-width: 1100px;
  margin: auto;
}

h1 {
  font-size: 2.5rem;
  color: #0c4a6e;
  text-align: center;
  margin-bottom: 20px;
}

.intro {
  text-align: center;
  font-size: 1.1rem;
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
  padding: 25px;
  border-radius: 15px;
  width: 240px;
  text-align: center;
  box-shadow: 0 6px 20px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.15);
}

.card img {
  width: 60px;
  margin-bottom: 15px;
}

.card h2 {
  color: #0c4a6e;
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.card p {
  font-size: 0.95rem;
  line-height: 1.4;
}
</style>

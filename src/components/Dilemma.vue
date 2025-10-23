<template>
  <section class="dilemma">
    <div class="container">
      <h1>Nosso Dilema</h1>
      <p class="intro">
        Explorar os 7 mares mantendo conforto, segurança e sustentabilidade é o desafio que nos move todos os dias.
      </p>

      <div class="cards">
        <div class="card">
          <Compass class="icon" />
          <h2>Exploração</h2>
          <p>
            Ampliar rotas e experiências únicas pelo mundo, sem comprometer o conforto dos passageiros.
          </p>
        </div>

        <div class="card">
          <Armchair class="icon" />
          <h2>Conforto</h2>
          <p>
            Garantir viagens agradáveis, com acomodações modernas, serviços personalizados e entretenimento a bordo.
          </p>
        </div>

        <div class="card">
          <Leaf class="icon" />
          <h2>Sustentabilidade</h2>
          <p>
            Operar de forma eco-friendly, preservando o meio ambiente e respeitando os oceanos que exploramos.
          </p>
        </div>

        <div class="card">
          <ShieldCheck class="icon" />
          <h2>Segurança</h2>
          <p>
            Manter protocolos de segurança rigorosos para passageiros e tripulação em todas as viagens.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { Compass, Leaf, ShieldCheck, Armchair } from "lucide-vue-next";

export default {
  name: "Dilemma",
  components: {
    Compass,
    Leaf,
    ShieldCheck,
    Armchair,
  },
};
</script>

<style scoped>
.dilemma {
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
  padding: 25px;
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

.icon {
  width: 60px;
  height: 60px;
  color: #0c4a6e;
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

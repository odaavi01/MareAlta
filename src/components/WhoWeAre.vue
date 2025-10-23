<template>
  <section class="who-we-are">
    <div class="container">
      <h1>Quem Somos</h1>
      <p class="intro">
        Somos a <strong>MaréAlta Cruises</strong>, pioneiros em experiências marítimas inesquecíveis no Brasil.
        Desde 2010, conectamos pessoas e destinos através de cruzeiros que unem conforto, sofisticação e sustentabilidade.
      </p>

      <div class="content">
        <div class="text">
          <h2>Nossa Missão</h2>
          <p>
            Levar cada passageiro a uma jornada única — onde o mar encontra o conforto, e a viagem se transforma em lembrança.
          </p>

          <h2>O que Fazemos</h2>
          <p>
            Operamos rotas exclusivas pelos principais portos do Brasil e da América do Sul. Oferecemos pacotes personalizados,
            entretenimento a bordo e uma equipe pronta para fazer parte da sua melhor viagem.
          </p>

          <h2>Por que Escolher a MaréAlta?</h2>
          <ul>
            <li>🌊 Experiência de mais de 10 anos em cruzeiros nacionais.</li>
            <li>🛳️ Frota moderna com tecnologia sustentável.</li>
            <li>🎶 Entretenimento e gastronomia premiados.</li>
            <li>💙 Atendimento humanizado e exclusivo.</li>
          </ul>
        </div>

        <div class="image">
          <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&q=80&w=800" alt="Cruzeiro no mar" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "WhoWeAre",
};
</script>

<style scoped>
.who-we-are {
  background: linear-gradient(to bottom, #f7fafc, #e2e8f0);
  padding: 60px 20px;
  color: #1a202c;
  font-family: 'Poppins', sans-serif;
}

.container {
  max-width: 1000px;
  margin: auto;
}

h1 {
  font-size: 2.5rem;
  color: #0c4a6e;
  margin-bottom: 20px;
  text-align: center;
}

.intro {
  text-align: center;
  font-size: 1.1rem;
  margin-bottom: 40px;
}

/* Remove borda preta transparente da palavra MaréAlta Cruises */
.intro strong {
  font-weight: 700 !important;
  color: #0288d1 !important;
  text-shadow: none !important;
  -webkit-text-stroke: 0 !important; /* remove contorno preto no Chrome/Safari */
}

.content {
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
  align-items: center;
}

.text {
  flex: 1;
  min-width: 300px;
}

.text h2 {
  color: #0c4a6e;
  margin-top: 20px;
  font-size: 1.3rem;
}

.text p {
  margin: 10px 0;
  line-height: 1.6;
}

.text ul {
  margin-top: 10px;
  list-style: none;
  padding: 0;
}

.text li {
  background: #e0f2fe;
  padding: 8px 12px;
  border-radius: 10px;
  margin-bottom: 8px;
}

.image {
  flex: 1;
  text-align: center;
}

.image img {
  max-width: 100%;
  border-radius: 15px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
}
</style>

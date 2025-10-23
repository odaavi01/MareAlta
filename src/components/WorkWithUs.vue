<template>
  <section class="work-section">
    <h2 class="title">Trabalhe Conosco</h2>
    <p class="subtitle">Confira as vagas abertas e embarque nessa jornada conosco!</p>

    <div class="job-list">
      <div v-for="(job, index) in jobs" :key="index" class="job-card">
        <h3>{{ job.title }}</h3>
        <p>{{ job.shortDescription }}</p>
        <button @click="selectJob(index)">Ver vaga</button>
      </div>
    </div>

    <!-- Modal de detalhes da vaga -->
    <div v-if="selectedJob !== null" class="modal-overlay" @click.self="closeModal">
      <div class="modal">
        <h3>{{ jobs[selectedJob].title }}</h3>
        <p><strong>Descrição:</strong> {{ jobs[selectedJob].description }}</p>
        <p><strong>Requisitos:</strong> {{ jobs[selectedJob].requirements }}</p>
        <p><strong>Salário:</strong> {{ jobs[selectedJob].salary }}</p>

        <button @click="showForm = true">Inscrever-se</button>
        <button class="secondary" @click="closeModal">Fechar</button>

        <!-- Formulário de inscrição -->
        <div v-if="showForm" class="form-container">
          <input v-model="form.name" type="text" placeholder="Seu nome completo" />
          <input v-model="form.email" type="email" placeholder="Seu e-mail" />
          <input v-model="form.phone" type="tel" placeholder="Seu telefone" />
          <button @click="submitApplication">Enviar candidatura</button>
        </div>

        <p v-if="submitted" class="success-message">
          Sua candidatura foi finalizada com sucesso! Boa sorte 🚀
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "WorkWithUs",
  data() {
    return {
      selectedJob: null,
      showForm: false,
      submitted: false,
      form: { name: "", email: "", phone: "" },
      jobs: [
        {
          title: "Atendente de Cruzeiro",
          shortDescription: "Auxilie nossos passageiros a bordo com excelência.",
          description: "Responsável por atender os hóspedes e garantir uma boa experiência a bordo.",
          requirements: "Boa comunicação, simpatia e disponibilidade para viagens.",
          salary: "R$ 2.500,00"
        },
        {
          title: "Garçom / Garçonete",
          shortDescription: "Sirva nossos hóspedes com qualidade e cordialidade.",
          description: "Responsável por servir alimentos e bebidas durante os cruzeiros.",
          requirements: "Experiência prévia em atendimento será um diferencial.",
          salary: "R$ 2.200,00"
        },
        {
          title: "Técnico de TI Embarcado",
          shortDescription: "Mantenha os sistemas do navio funcionando perfeitamente.",
          description: "Atuar na manutenção de sistemas e redes a bordo.",
          requirements: "Formação técnica ou superior em TI. Experiência com suporte técnico.",
          salary: "R$ 4.000,00"
        },

        {
          title: "Chef de Cozinha",
          shortDescription: "Comande a cozinha do navio e surpreenda nossos hóspedes.",
          description: "Responsável pela coordenação da equipe de cozinha e preparo dos pratos.",
          requirements: "Formação em gastronomia e experiência comprovada.",
          salary: "R$ 6.000,00"
        },
        {
          title: "Fotógrafo de Cruzeiro",
          shortDescription: "Registre momentos inesquecíveis durante as viagens.",
          description: "Fotografar hóspedes e eventos a bordo.",
          requirements: "Experiência em fotografia e edição de imagens.",
          salary: "R$ 3.500,00"
        },
        {
          title: "Músico / Banda",
          shortDescription: "Traga música e diversão para nossos cruzeiros.",
          description: "Apresentar-se em eventos e festas no navio.",
          requirements: "Experiência com apresentações ao vivo.",
          salary: "R$ 4.500,00"
        },
        {
          title: "Enfermeiro(a) de Bordo",
          shortDescription: "Cuide da saúde dos passageiros e tripulação.",
          description: "Atuar no atendimento médico e primeiros socorros.",
          requirements: "Formação em enfermagem e registro ativo no COREN.",
          salary: "R$ 5.000,00"
        },
        {
          title: "Recepcionista",
          shortDescription: "Receba nossos hóspedes com simpatia e eficiência.",
          description: "Realizar check-in, check-out e atendimento geral.",
          requirements: "Inglês intermediário e boa comunicação.",
          salary: "R$ 2.800,00"
        },
        {
          title: "Segurança de Cruzeiro",
          shortDescription: "Garanta a segurança e tranquilidade a bordo.",
          description: "Monitorar áreas do navio e prestar suporte em emergências.",
          requirements: "Experiência prévia em segurança será valorizada.",
          salary: "R$ 3.200,00"
        },
      ],
    };
  },
  methods: {
    selectJob(index) {
      this.selectedJob = index;
      this.showForm = false;
      this.submitted = false;
    },
    closeModal() {
      this.selectedJob = null;
    },
    submitApplication() {
      this.submitted = true;
      this.showForm = false;
      this.form = { name: "", email: "", phone: "" };
    },
  },
};
</script>

<style scoped>
.work-section {
  padding: 50px 20px;
  text-align: center;
  background: linear-gradient(to bottom, #e0f7fa, #ffffff);
  color: #003366;
}

.title {
  font-size: 2rem;
  margin-bottom: 10px;
  font-weight: 700;
}

.subtitle {
  font-size: 1.1rem;
  margin-bottom: 40px;
  color: #004d66;
}

.job-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
  gap: 20px;
  justify-content: center;
}

.job-card {
  background: white;
  border-radius: 16px;
  padding: 20px;
  box-shadow: 0 4px 15px rgba(0, 51, 102, 0.1);
  transition: 0.3s;
}

.job-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 51, 102, 0.15);
}

.job-card h3 {
  color: #003366;
  font-size: 1.3rem;
  margin-bottom: 10px;
}

button {
  background: #0077b6;
  border: none;
  color: white;
  padding: 10px 18px;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: #005f8f;
}

button.secondary {
  background: #ccc;
  color: #003366;
  margin-left: 10px;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 30, 60, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10;
}

.modal {
  background: white;
  border-radius: 20px;
  padding: 30px;
  max-width: 600px;
  width: 90%;
  text-align: left;
  box-shadow: 0 10px 30px rgba(0, 30, 60, 0.3);
}

.form-container {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

input {
  padding: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
}

.success-message {
  margin-top: 15px;
  color: #007f3f;
  font-weight: bold;
}
</style>

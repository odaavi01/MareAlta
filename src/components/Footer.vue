<template>
  <footer class="site-footer">
    <div>© {{ year }} MaréAlta Cruzeiros</div>
    <div class="socials">Siga-nos nas redes — @marealta</div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() { return { year: new Date().getFullYear() } }
}
</script>

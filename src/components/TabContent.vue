<template>
  <div class="tab-content">
    <h2>{{ title }}</h2>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  props: ['title', 'text']
}
</script>

<style scoped>
.tab-content {
  padding: 20px;
  background-color: rgba(255,255,255,0.8);
  border-radius: 10px;
  margin-bottom: 20px;
}
.tab-content h2 {
  color: #01579b;
  margin-bottom: 10px;
}
</style>

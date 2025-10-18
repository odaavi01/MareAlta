<template>
  <transition name="panel-fade">
    <div v-if="open" class="panel">
      <header class="panel-header">
        <h3>{{ title }}</h3>
        <button class="close" @click="$emit('close')">✕</button>
      </header>
      <section class="panel-body">
        <slot />
      </section>
    </div>
  </transition>
</template>

<script>
export default { name: 'Panel', props: ['title', 'open'] }
</script>

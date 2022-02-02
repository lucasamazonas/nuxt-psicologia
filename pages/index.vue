<template>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  async asyncData ({ $axios }) {
    await $axios.$get('http://localhost/pscologia/api-psicologia/public/sanctum/csrf-cookie')
      .then(() => {
        console.log('Proteção csrf ativada.')
      })
      .catch(() => {
        console.log('Erro ao solicitar proteção csrf.')
      })
  }
})
</script>

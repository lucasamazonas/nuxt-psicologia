<template>
  <div>
    Olá mundo!
  </div>
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

<template>
  <div class="home">
    <h1
      :style="colorContador"
    >{{ titulo }}: {{ contador }}</h1>
    <button @click="accionIncrementar">Aumentar</button>
    <BtnDisminuir />
  </div>
</template>

<script>

import BtnDisminuir from '@/components/BtnDisminuir'
import {mapState, mapMutations, mapActions} from 'vuex'

export default {
  name: 'Home',
  data() {
    return {
      titulo: "Mi Contador Vuex"
    }
  },
  computed: {
    ...mapState(['contador']),
    colorContador() {
      return [this.contador > 100 ? {'color': 'green'} : {'color': 'red'}]
    }
  },
  methods: {
    ...mapActions(['accionIncrementar'])
  },
  components: {
    BtnDisminuir
  }
}
</script>

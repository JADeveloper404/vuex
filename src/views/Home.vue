<template>
  <div class="home">
    <h1
      :style="colorContador"
    >{{ titulo }}: {{ contador }}</h1>
  </div>
</template>

<script>

import {mapState} from 'vuex'

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
  components: {
    
  }
}
</script>

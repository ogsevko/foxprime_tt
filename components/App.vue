<template>
  <div class="app">
    <AppHeader />
    <AddCity />
  </div>
</template>

<script>
import AppHeader from './AppHeader'
import AddCity from './AddCity'

export default {
  name: 'App',
  components: {
    AppHeader,
    AddCity
  },
  data () {
    return {
      cities: []
    }
  },
  methods: {
    addCity (newCity) {
      this.cities = [...this.cities, newCity]
    }
  }
}
</script>

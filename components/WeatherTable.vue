<template>
  <table class="table">
    <tr v-for="city in cities" :key="city.id">
      <td>{{ city.name }}</td>
      <td>{{ city.weather[0].main }}</td>
      <td>{{ city.main.temp }}</td>
    </tr>
  </table>
</template>

<script>
export default {
  name: 'WeatherTable',
  props: {
    cities: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.table {
  color: white;
  border: none;
  margin: 0 auto;
}
</style>

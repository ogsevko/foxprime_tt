<template>
  <v-input>
    <v-text-field
      autofocus="true"
      outlined="true"
      rounded="true"
      full-width="false"
    />
  </v-input>
</template>

<script>
export default {
  name: 'AddCity'
}
</script>

<style scoped lang="scss">
.city {
  &__input {
    width: 45%;
  }
}
</style>

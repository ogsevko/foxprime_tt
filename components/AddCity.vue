<template>
  <v-input>
    <v-text-field
      v-model="name"
      autofocus
      outlined
      rounded
      single-line
      @keyup.enter="addCity"
    />
  </v-input>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'

export default {
  name: 'AddCity',
  data () {
    return {
      name: ''
    }
  },
  methods: {
    addCity (event) {
      event.preventDefault()

      const newCity = {
        id: uuidv4(),
        name: this.name
      }

      this.$emit('add-city', newCity)

      this.name = ''
    }
  }
}
</script>

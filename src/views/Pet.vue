<template>
   <div>
      <h2>{{animal.name}} ({{this.$route.params.species === 'dogs' ? 'Dog' : 'Cat'}})</h2>
      <p>Age: {{ animal.age }} years old</p>
      <p>Breed: {{animal.breed}}</p>
   </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted () {
    this.animal = this[this.$route.params.species][this.$route.params.id]
  }
}
</script>

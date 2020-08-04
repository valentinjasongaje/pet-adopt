<template>
  <div>
    <b-container>
      <h1>Dogs for Adoption</h1>
      <b-table striped hover :items="dogs">
        <template v-slot:cell(name)="data">
          <!-- `data.value` is the value after formatted by the Formatter -->
          <a :href="`/pets/dogs/${data.index}`">{{ data.value }}</a>
        </template>
      </b-table>
    </b-container>
  </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {}
  },
  computed: {
    ...mapState(['dogs'])
  }
}
</script>

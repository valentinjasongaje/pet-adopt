<template>
  <div>
    <b-container>
      <h1>{{ species }} for Adoption</h1>
      <b-table striped hover :items="pets">
        <template v-slot:cell(name)="data">
          <!-- `data.value` is the value after formatted by the Formatter -->
          <a :href="`/pets/${species}/${data.index}`">{{ data.value }}</a>
        </template>
      </b-table>
    </b-container>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  props:{
      species: String,
      pets: Array
  }
}
</script>

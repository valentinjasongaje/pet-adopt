<template>
  <div>
    <b-container>
      <h1>Cats for Adoption</h1>
      <b-table striped hover :items="cats">
        <template v-slot:cell(name)="data">
          <!-- `data.value` is the value after formatted by the Formatter -->
          <a :href="`/pets/${data.value}`">{{ data.value }}</a>
        </template>
      </b-table>
    </b-container>
  </div>
</template>

<script>
import cats from '@/data/cats'
export default {
  data () {
    return {
      cats
    }
  }
}
</script>

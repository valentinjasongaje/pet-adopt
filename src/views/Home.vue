<template>
  <div class="home">
    <button @click="toggleForm" class="btn btn-primary">Add New Pet</button><br><br>
    <b-container>
    <b-form @submit.prevent="handeSubmit" v-if="showPetForm">
        <b-form-input
          id="input-1"
          v-model="formData.name"
          type="text"
          required
          placeholder="Pet name"
        ></b-form-input>
      <b-form-group id="input-group-2" label="Age:" label-for="input-2">
        <b-form-input id="input-2" type="number" v-model="formData.age" required placeholder="Enter Age"></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="Species:" label-for="input-3">
        <b-form-select id="input-3" v-model="formData.species" :options="['cats','dogs']" required></b-form-select>
      </b-form-group>

      <b-button type="submit" variant="primary">Submit</b-button>
    </b-form>
    </b-container>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: 'home',
  data () {
    return {
      formData: {
        name: '',
        age: 0,
        species: null
      },
      showPetForm: false
    }
  },
  methods: {
    ...mapActions([
      'addPet'
    ]),
    toggleForm () {
      this.showPetForm = !this.showPetForm
    },
    handeSubmit () {
      const { species, age, name } = this.formData
      const payload = {
        species,
        pet: {
          name,
          age
        }
      }
      this.addPet(payload)
      this.formData = {
        name: '',
        age: 0,
        species: null
      }
    }
  }
}
</script>

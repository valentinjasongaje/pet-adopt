<template>
  <div>
    <PetTable
    species="cats"
    :pets="cats"
    />
  </div>
</template>
<script>
import { mapState, mapGetters } from 'vuex'
import PetTable from '@/components/PetTable.vue'
export default {
  components: {
    PetTable
  },
  data () {
    return {}
  },
  computed: {
    ...mapState(['cats']),
    ...mapGetters(['getAllCats'])
  }
}
</script>

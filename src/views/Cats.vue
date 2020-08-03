<template>
  <div>
    <b-container>
      <b-table striped hover :items="cats" />
    </b-container>
  </div>
</template>
<script>
import cats from "@/data/cats"
export default {
  data() {
    return {
      cats,
    };
  },
};
</script>

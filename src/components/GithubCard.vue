<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ userToPrint: Object }>()

const count = ref(0)
</script>

<template>
  <div class="col">
    <div class="card" style="width: 18rem;">
      <img :src="userToPrint.avatar_url" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">{{ userToPrint.login }}</h5>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        <a :href="userToPrint.html_url" class="btn btn-primary">View Profile</a>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>

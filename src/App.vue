<script setup lang="ts">
import GithubCard from "./components/GithubCard.vue";
import AppHeader from "./components/layout/AppHeader.vue";
import AppFooter from "./components/layout/AppFooter.vue";
import {onMounted, ref} from "vue";

const users =ref([]);
async function getRandomGitHubProfile() {
  // Ottieni l'elenco degli utenti (puoi modificare l'endpoint per cambiare il set di utenti)
  const response = await fetch('https://api.github.com/users?since='+  Math.floor(Math.random() * 1000)) ;
   users.value = await response.json();

  // Mostra i dettagli dell'utente
  console.log(users);
}

onMounted(() => {
  getRandomGitHubProfile();
});


</script>

<template>
<AppHeader></AppHeader>

  <div class="container ">
    <h1 class="text-center">Elenco Cards GitHub</h1>
    <div class="row">
      <GithubCard v-for="user in users" :userToPrint="user" />
    </div>
  </div>
  <AppFooter></AppFooter>
</template>

<style scoped>

</style>

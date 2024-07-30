<template>
  <Head_er />
  <div class="error-container">
    <img
      src="../assets/images/oops.png"
      alt="Illustration de page d'erreur 404 avec texte 'Oops'"
    />
    <h1 class="error-title">Error 404 - Page Not Found</h1>
    <p class="error-message">Désolé,nous ne trouvons pas la page demandée.</p>
    <router-link class="link" to="/">Retourner à la page d'accueil</router-link>
  </div>
  <Foot_er />
</template>

<script setup>
import Head_er from "@/components/Head_er.vue";
import Foot_er from "@/components/Foot_er.vue";
</script>

<style scoped>
.error-container {
  text-align: center;
  margin: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 30 rem;
}

img {
  width: 100%;
  max-width: 300px;
}

.error-title {
  font-size: 2rem;
  margin-top: 20px;
  margin-bottom: 10px;
}

.error-message {
  font-size: 1rem;
  margin-bottom: 20px;
}

.link {
  font-size: 1rem;
  color: rgba(182, 121, 182, 0.849);
  font-weight: bold;
  text-decoration: none;
  transition: color 0.3s;
}

.link:hover {
  color: #551a8b;
}
</style>

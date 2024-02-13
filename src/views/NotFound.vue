<template>
  <div>
    <img src="../assets/images/oops.png" alt="oops" />
    <h1>Error 404 - Page Not Found</h1>
    <p>Désolé,nous ne trouvons pas la page demandée.</p>
    <router-link class="link" to="/">Retourner à la page d'accueil</router-link>
  </div>
</template>

<script setup></script>

<style scoped>
div {
  text-align: center;
}

img {
  width: 100%;
  max-width: 300px;
}

h1 {
  font-size: 40px;
  margin-top: 20px;
  margin-bottom: 10px;
}

p {
  font-size: 20px;
  margin-bottom: 20px;
}

.link {
  font-size: 20px;
  color: rgba(182, 121, 182, 0.849);
  font-weight: bold;
  text-decoration: none;
}
</style>

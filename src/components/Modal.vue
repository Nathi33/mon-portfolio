<template>
  <div class="bloc-modal" v-if="modalVisible">
    <div class="overlay-modal" @click="toggleModal"></div>

    <div class="modal-card">
      <div class="modal-card-left">
        <img :src="modalImage" alt="Image projet" />
      </div>
      <div class="modal-card-right">
        <button class="btn-modal" @click="toggleModal">&times;</button>
        <h4>{{ titre }}</h4>
        <div class="date">
          <img src="../assets/images/calendrier.png" alt="calendrier" />
          <p>{{ date }}</p>
        </div>
        <h5>Description</h5>
        <p>{{ description }}</p>
        <h5>Technologies Utilisées</h5>
        <ul>
          <li v-for="techno in technologies" :key="techno">{{ techno }}</li>
        </ul>
        <h5>Lien</h5>
        <a target="_blank" :href="lien">{{ lienTexte }}</a>
      </div>
    </div>
  </div>
</template>

<script setup>
// Définition des props
const {
  modalVisible,
  titre,
  date,
  description,
  technologies,
  lien,
  lienTexte,
  modalImage,
} = defineProps([
  "modalVisible",
  "titre",
  "date",
  "description",
  "technologies",
  "lien",
  "lienTexte",
  "modalImage",
]);

// Émetteur d'événements
const emits = defineEmits(["toggleModal"]);

// Fonction pour fermer la modal
const toggleModal = () => {
  // Émettre l'événement 'toggleModal' vers le parent
  emits("toggleModal");
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}

a:hover {
  text-decoration: underline;
}

.bloc-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 100;
}

.overlay-modal {
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.modal-card {
  background-color: white;
  color: #333;
  width: 40%;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
  position: fixed;
  transition: all 0.5s;
}

.btn-modal {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: #333;
  color: #fff;
  border: 1px solid black;
  cursor: pointer;
  width: 25px;
  height: 25px;
  border-radius: 50%;
}

.date {
  display: flex;
  justify-content: flex-start;
}

.date img {
  width: 20px;
  height: auto;
  object-fit: contain;
  margin-right: 30px;
}

.modal-card-left img {
  width: 100%;
  height: auto;
  object-fit: contain;
}
</style>

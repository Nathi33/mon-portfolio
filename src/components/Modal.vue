<template>
  <div class="bloc-modal" v-if="modalVisible">
    <div class="overlay-modal" @click="toggleModal"></div>

    <div class="modal-card">
      <figure class="modal-card-left">
        <!-- Boucle pour générer les images à partir du tableau images -->
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image.src"
          alt="Image du projet"
        />
      </figure>

      <div class="modal-card-right">
        <button class="btn-modal" @click="toggleModal">&times;</button>
        <h4>{{ titre }}</h4>
        <figure class="date">
          <img src="../assets/images/calendrier.png" alt="logo calendrier" />
          <p>{{ date }}</p>
        </figure>
        <h5>Description</h5>
        <p>{{ description }}</p>
        <h5>Technologies Utilisées</h5>
        <ul>
          <!-- Chaque élément de la liste li aura le texte correspondant à l'élément actuel du tableau technologies -->
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
  images,
} = defineProps([
  "modalVisible",
  "titre",
  "date",
  "description",
  "technologies",
  "lien",
  "lienTexte",
  "images",
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
img {
  width: 20px;
  height: auto;
  object-fit: contain;
}

a {
  text-decoration: none;
  color: black;
}

a:hover {
  text-decoration: underline;
  font-weight: bold;
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
  display: flex;
  width: 60%;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
  position: fixed;
  transition: all 0.5s;
  overflow-y: auto;
}

.modal-card-right {
  padding-left: 20px;
}

.modal-card-left {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
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

@media screen and (max-width: 750px) {
  .modal-card {
    width: 90%;
    height: 80%;
  }
}
</style>

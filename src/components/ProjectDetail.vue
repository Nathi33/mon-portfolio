<template>
  <section id="projectDetail">
    <div class="project_global">
      <h1 class="project_title">Projets</h1>

      <div class="project">
        <div class="card" data-category="cv">
          <img src="../assets/images/cv.png" alt="cv" />
          <h3>Mon Curriculum Vitae</h3>
          <!--Overlay = recouvrement -->
          <div class="card_overlay">
            <!--Utilisation de @click pour déclencher une méthode-->
            <button class="btn-open" @click="openModal('Contenu CV')">+</button>
            <!-- Passer modalVisible comme prop à Essai et écouter l'évènement closeModal -->
          </div>
        </div>

        <div class="card" data-category="cahier_charges">
          <img src="../assets/images/La socketterie.png" alt="socketterie" />
          <h3>Cahier des Charges : La Socketterie</h3>
          <div class="card_overlay">
            <button class="btn-open" @click="openModal('Contenu CDC')">
              +
            </button>
          </div>
        </div>

        <div class="card" data-category="dynamiser_commentaire">
          <img src="../assets/images/Commentaire.png" alt="commentaite" />
          <h3>Dynamisme d'un espace commentaire</h3>
          <div class="card_overlay">
            <button class="btn-open" @click="openModal('Contenu DEC')">
              +
            </button>
          </div>
        </div>

        <Modal
          :modalVisible="modalVisible"
          :titre="modalTitre"
          :date="modalDate"
          :description="modalDescription"
          :technologies="modalTechnologies"
          :lien="modalLien"
          :lienTexte="modalLienTexte"
          :modalImage="modalImage"
          @toggleModal="toggleModal"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import Modal from "@/components/Modal.vue";

//Initialisation des refs pour les propriétés de la modal
const modalVisible = ref(false);
const modalTitre = ref("");
const modalDate = ref("");
const modalDescription = ref("");
const modalTechnologies = ref([]);
const modalLien = ref("");
const modalLienTexte = ref("");
const modalImage = ref("");

//Fonction pour ouvrir la modal
const openModal = (titre) => {
  if (titre === "Contenu CV") {
    modalVisible.value = true;
    modalTitre.value = "Mon Curriculum Vitae";
    modalDate.value = "Juillet 2023";
    modalDescription.value =
      "Le projet de réalisation du CV est le premier réalisé durant ma formation au sein du Centre Européen de Formation. L'objectif était de mettre en application mes connaissances en HTML et CSS acquises afin de faire créer un CV en ligne dynamique.";
    modalTechnologies.value = ["HTML", "CSS", "GitHub"];
    modalLien.value = "https://github.com/Nathi33/depot-cv.git";
    modalLienTexte.value = "Mon CV";
    modalImage.value = "../assets/images/cv-detail1.png";
  } else if (titre === "Contenu CDC") {
    modalVisible.value = true;
    modalTitre.value = "Réalisation Cahier des Charges";
    modalDate.value = "Octobre 2023";
    modalDescription.value =
      "Etablissement d'un cahier des charges pour un projet de création de site web e-commerce pour une entreprise de vente de chaussettes. ";
    modalTechnologies.value = ["Word", "Miro", "GlooMaps"];
    modalLien.value =
      "https://drive.google.com/file/d/1-TaB3q3MqGEAv8nX8KMRMBaqoJvCidJt/view?usp=sharing";
    modalLienTexte.value = "Cahier des charges";
    modalImage.value = "../assets/images/logo-linked.png";
  } else if (titre === "Contenu DEC") {
    modalVisible.value = true;
    modalTitre.value = "Dynamisme du Commentaire";
    modalDate.value = "Novembre 2023";
    modalDescription.value =
      "Cette mission consiste à dynamiser un espace commentaire afin de faire apparaître un nouveau commentaire directement dans la liste des commentaires au moment où on valide le formulaire, avec réinitialisation des champs, sans aucun rechargement de la page et affichage d'un message d'erreur.";
    modalTechnologies.value = ["HTML", "CSS", "JavaScript", "GitHub"];
    modalLien.value = "https://github.com/Nathi33/dynamiser_commentaire.git";
    modalLienTexte.value = "Dynamiser un commentaire";
    modalImage.value = "../assets/images/commentaire-detail.png";
  }

  //Afficher la modal
  modalVisible.value = true;
};

//Fonction pour fermer la modal
const toggleModal = () => {
  modalVisible.value = !modalVisible.value;
};
</script>

<style scoped>
.project_global {
  padding-top: 40px;
  padding-bottom: 60px;
}
.project_title {
  text-align: center;
  font-size: 50px;
  padding-bottom: 50px;
}
.project img {
  width: 150px;
  height: 230px;
}
.project {
  display: flex;
  justify-content: space-around;
  padding-bottom: 30px;
}

.card {
  background-color: #ffffff;
  width: 216px;
  margin-top: 10px;
  padding-top: 20px;
  padding-bottom: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-transform: uppercase;
  /* L'élément est positionné dans le flux normal du document puis décalé, par rapport à lui-même */
  position: relative;
  /* Ombre portée avec une légère transparence */
  box-shadow: 0 0 7px rgba(0, 0, 0, 0.5);
  border: solid #eeeeee 1px;
  /* Tout contenu dépassant les dimensions de la boîte sera masqué */
  overflow: hidden;
}

.card h3 {
  font-size: 12px;
  text-align: center;
}
.card_overlay {
  background-color: rgba(0, 0, 0, 0.8);
  /* L'élément est retiré du flux normal et aucun espace n'est créé pour l'élément sur la page. Il est ensuite positionné par rapport à son ancêtre le plus proche */
  position: absolute;
  top: 0;
  /* Ordre d'empilement des éléments, où 0 est la valeur la plus basse */
  z-index: 0;
  width: 100%;
  height: 100%;
  /*Permet effet de style de l'overlay*/
  top: 110%;
  transition: all 0.3s;
}
.btn-open {
  font-size: 75px;
  background-color: transparent;
  border: none;
  color: white;
  padding-top: 50%;
  padding-left: 40%;
  cursor: pointer;
}

.card:hover {
  /*Effet de style de la carte*/
  transform: scale(1.1);
  box-shadow: 12px 12px 5px rgba(106, 206, 219, 0.5);
  z-index: 10;
}
.card:hover .card_overlay {
  /*Effet de style de l'overlay*/
  top: 0;
}
</style>

<template>
  <section id="projectDetail">
    <div class="project_global">
      <h2 class="project_title">Projets</h2>

      <div class="project">
        <!-- Boucle pour générer les modales à partir du tableau projects -->
        <div
          class="card"
          v-for="(project, index) in projects"
          :key="index"
          :data-category="project.category"
        >
          <img :src="project.imgSrc" :alt="project.imgAlt" />
          <h3>{{ project.title }}</h3>
          <div class="card_overlay">
            <button class="btn-open" @click="openModal(project)">+</button>
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
          :images="modalImages"
          @toggleModal="toggleModal"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import Modal from "@/components/Modal.vue";

import img1 from "../assets/images/cv.png";
import img2 from "../assets/images/la-socketterie.png";
import img3 from "../assets/images/Commentaire.png";
import img4 from "../assets/images/cv-detail1.png";
import img5 from "../assets/images/cv-detail2.png";
import img6 from "../assets/images/CDC-detail1.png";
import img7 from "../assets/images/CDC-detail2.png";
import img8 from "../assets/images/DEC-detail1.png";
import img9 from "../assets/images/DEC-detail2.png";

// Définition des projets avec les données nécessaires pour chaque projet
const projects = [
  {
    category: "cv",
    imgSrc: img1,
    imgAlt: "Aperçu du CV de Nath Drnt",
    title: "Mon Curriculum Vitae",
    modalData: {
      titre: "Mon Curriculum Vitae",
      date: "Juillet 2023",
      description:
        "Cette réalisation est le premier projet fait durant mon apprentissage au sein du Centre Européen de Formation. L'objectif était de mettre en application mes connaissances en HTML et CSS acquises afin de créer un CV en ligne dynamique.",
      technologies: ["HTML", "CSS", "GitHub"],
      lien: "https://github.com/Nathi33/depot-cv.git",
      lienTexte: "Mon CV",
      images: [
        {
          src: img4,
          alt: "Détail du CV - section 1",
        },
        {
          src: img5,
          alt: "Détail du CV - section 2",
        },
      ],
    },
  },
  {
    category: "cahier_charges",
    imgSrc: img2,
    imgAlt: "Aperçu du projet la Socketterie",
    title: "Réalisation Cahier des Charges",
    modalData: {
      titre: "Réalisation Cahier des Charges",
      date: "Octobre 2023",
      description:
        "Etablissement d'un cahier des charges dans un projet de création de site web e-commerce pour une entreprise de vente de chaussettes.",
      technologies: ["Word", "Miro", "GlooMaps"],
      lien: "https://drive.google.com/file/d/1-TaB3q3MqGEAv8nX8KMRMBaqoJvCidJt/view?usp=sharing",
      lienTexte: "Cahier des charges",
      images: [
        {
          src: img6,
          alt: "Détail du projet La socketterie - section 1",
        },
        {
          src: img7,
          alt: "Détail du projet La socketterie - section 2",
        },
      ],
    },
  },
  {
    category: "dynamiser_commentaire",
    imgSrc: img3,
    imgAlt: "Aperçu du projet dynamiser un commentaire",
    title: "Dynamiser un Commentaire",
    modalData: {
      titre: "Dynamiser un Commentaire",
      date: "Novembre 2023",
      description:
        "Cette mission consiste à dynamiser un espace commentaire afin d'y faire apparaître un nouveau directement dans la liste au moment où l'on valide le formulaire, avec réinitialisation des champs, sans aucun rechargement de la page et affichage d'un message d'erreur.",
      technologies: ["HTML", "CSS", "JavaScript", "GitHub"],
      lien: "https://github.com/Nathi33/dynamiser_commentaire.git",
      lienTexte: "Dynamiser un commentaire",
      images: [
        {
          src: img8,
          alt: "Détail du projet Dynamiser un commentaire - section 1",
        },
        {
          src: img9,
          alt: "Détail du projet Dynamiser un commentaire - section 2",
        },
      ],
    },
  },
];

//Initialisation des refs pour les propriétés de la modal
const modalVisible = ref(false);
const modalTitre = ref("");
const modalDate = ref("");
const modalDescription = ref("");
const modalTechnologies = ref([]);
const modalLien = ref("");
const modalLienTexte = ref("");
const modalImages = ref([]);

//Fonction pour ouvrir la modal
const openModal = (project) => {
  modalVisible.value = true;
  modalTitre.value = project.modalData.titre;
  modalDate.value = project.modalData.date;
  modalDescription.value = project.modalData.description;
  modalTechnologies.value = project.modalData.technologies;
  modalLien.value = project.modalData.lien;
  modalLienTexte.value = project.modalData.lienTexte;
  modalImages.value = project.modalData.images;
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
  font-size: 0.875rem;
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

/* Ajustement pour petit écran */
@media screen and (max-width: 768px) {
  .project {
    flex-direction: column; /* Changer la direction de flex en colonne pour les petits écrans */
    align-items: center;
  }
}
</style>

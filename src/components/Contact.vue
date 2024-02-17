<template>
  <section id="contact">
    <div class="contact-container">
      <h1>Contact</h1>

      <form ref="formRef" action="#" class="form" @submit.prevent="submitForm">
        <label for="firstname">
          <input
            type="text"
            v-model="firstname"
            name="firstname"
            id="firstname"
            placeholder="Nom"
            required
        /></label>
        <label for="lastname">
          <input
            type="text"
            v-model="lastname"
            name="lastname"
            id="lastname"
            placeholder="Prénom"
          />
        </label>
        <label for="object">
          <input
            type="text"
            v-model="object"
            name="object"
            id="object"
            placeholder="Objet"
            required
          />
        </label>
        <label for="message">
          <textarea
            v-model="message"
            name="message"
            id="message"
            placeholder="Message"
            required
          ></textarea>
        </label>

        <input type="submit" class="btn" value="Envoyer" />
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const formRef = ref(null);

const router = useRouter();

//Déclaration des références des différents champs du formulaire
const firstname = ref("");
const lastname = ref("");
const object = ref("");
const message = ref("");

//Fonction pour envoyer le formulaire
const submitForm = () => {
  //Création du corps du mail
  const messageBody = `
          Nom: ${firstname.value} 
          Prénom: ${lastname.value}
          Objet: ${object.value}
          Message: ${message.value}`;

  //Création du lien mailto
  const mailtolink = `milano_134@hotmail.com?subject=Nouveau%20message%20du%20formulaire%20de%20contact&body=${encodeURIComponent(
    messageBody
  )}`;

  //Affichage de la confirmation d'envoi
  alert(
    "Votre message a bien été envoyé à l'adresse mail suivante : milano_134@hotmail.com!"
  );

  //Réinitialisation des champs du formulaire
  formRef.value.reset();
};
</script>

<style scoped>
h1 {
  font-size: 2.5rem;
}
.contact-container {
  background-color: rgba(182, 121, 182, 0.849);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-top: 30px;
  padding-bottom: 30px;
}

.form {
  max-width: 600px;
  width: 100%;
  padding: 20px;
  box-sizing: border-box; /* pour que le padding ne soit pas ajouté à la largeur du formulaire */
}

.form input,
.form textarea {
  display: block;
  width: 100%;
  padding: 8px;
  margin-bottom: 20px;
  border: black 2px solid;
}

.form textarea {
  min-height: 200px;
}

.form .btn {
  background-color: #fff;
  color: #333;
  width: auto;
  min-width: 160px;
  font-size: 20px;
  text-transform: uppercase;
}

.form .btn:hover {
  cursor: pointer;
  background-color: #333;
  color: #fff;
}

/* Ajustement pour les petits écrans */
@media screen and (max-width: 768px) {
  .form input,
  .form textarea {
    width: 100%; /* Utilise la largeur complète pour les écrans plus petits */
  }

  .form .btn {
    width: auto; /* Rétablit la largeur automatique pour les boutons */
  }
}
</style>

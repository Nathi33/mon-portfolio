<template>
  <section id="contact">
    <div class="contact-container">
      <h2>Contact</h2>

      <form ref="formRef" action="#" class="form" @submit.prevent="submitForm">
        <label for="firstname"
          >Nom
          <input
            type="text"
            v-model="firstname"
            name="firstname"
            id="firstname"
            placeholder="Nom"
            required
        /></label>
        <label for="lastname"
          >Prénom
          <input
            type="text"
            v-model="lastname"
            name="lastname"
            id="lastname"
            placeholder="Prénom"
          />
        </label>
        <label for="object"
          >Objet
          <input
            type="text"
            v-model="object"
            name="object"
            id="object"
            placeholder="Objet"
            required
          />
        </label>
        <label for="message"
          >Message
          <textarea
            v-model="message"
            name="message"
            id="message"
            placeholder="Message"
            required
          ></textarea
          >Message
        </label>

        <input type="submit" class="btn" value="Envoyer" />
      </form>

      <p v-if="formSubmitted" class="confirmation-message">
        Votre message a bien été envoyé !
      </p>
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
const formSubmitted = ref(false);

//Fonction pour envoyer le formulaire
const submitForm = () => {
  // Simule l'envoi du formulaire en affichant un message de confirmation
  formSubmitted.value = true;

  // Réinitialise les valeurs des champs du formulaire
  firstname.value = "";
  lastname.value = "";
  object.value = "";
  message.value = "";

  // Réinitialise les champs du formulaire
  formRef.value.reset();

  // Réininitialise le message d'envoi après 3 secondes
  setTimeout(() => {
    formSubmitted.value = false;
  }, 3000);
};
</script>

<style scoped>
h2 {
  font-size: 2.5rem;
}

label {
  color: transparent;
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

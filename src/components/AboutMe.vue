<template>
  <section id="aboutMe">
    <div class="aboutme">
      <div class="aboutme_img">
        <img src="../assets/images/photo.jpg" alt="photo de Profil" />
      </div>
      <div class="aboutme_description">
        <div class="description">
          <h1>A propos</h1>
          <p>
            Après de nombreuses années dans le secteur du paramédical et du
            secrétariat, j'ai décidé de donner un nouveau souffle à ma carrière
            et d'oser tenter l'aventure du "Développement Web".<br />
            J'ai commencé par suivre des formations dispensées sur internet via
            OpenCLassRooms ou encore Le Réacteur afin de m'initier au code.
            Cette première approche m'a permis de me conforter dans l'idée de
            faire du Développement ma nouvelle vocation. J'ai donc débuter ma
            formation de Développeur Web et Mobile au sein du Centre Européen de
            Formation. Depuis, je code quotidiennement avec chaque jour
            davantage de passion.<br />Si je ne suis encore que "junior" en
            développement, mon parcours professionnel m'a appris le travail en
            équipe, l'adaptation, la rigueur et l'écoute des besoins du
            client.<br />J'espère pouvoir mettre mon enthousiasme, mes
            compétences et ma créativité à votre disposition.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.description h1 {
  font-size: 50px;
}
.aboutme {
  padding-top: 100px;
  padding-bottom: 100px;
  display: flex;
}
.aboutme_img {
  display: flex;
}
.aboutme_img img {
  object-fit: contain;
  max-width: 80%;
  height: auto;
}
.aboutme_description {
  display: flex;
  padding-left: 80px;
  padding-right: 80px;
  text-align: justify;
}
.description {
  align-items: center;
}
</style>

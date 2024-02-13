<template>
  <section id="skills">
    <div class="skills">
      <h1>Compétences</h1>
      <div class="skills_description">
        <div class="technique">
          <h2>Compétences techniques</h2>
          <img src="../assets/images/Logos.jpg" alt="logos compétences" />
        </div>
        <div class="transverse">
          <h2>Compétences transversales</h2>
          <ul>
            <li>Autonomie</li>
            <li>Rigueur et efficacité</li>
            <li>Aisance relationnelle</li>
            <li>Ecoute et adaptabilité</li>
            <li>Travail en équipe</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.skills h1 {
  font-size: 50px;
  text-align: center;
  padding-bottom: 30px;
}
.skills {
  padding: 40px 20px 60px;
  background-color: rgba(182, 121, 182, 0.849);
}
.skills_description {
  display: flex;
  justify-content: space-around;
}
.technique {
  border: solid black 1px;
  background-color: aliceblue;
  padding: 0 10px 0 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.transverse {
  border: solid black 1px;
  background-color: aliceblue;
  padding: 10px;
  line-height: 40px;
}
.technique img {
  width: 200px;
}
</style>

<template>
  <section id="welcome">
    <div class="hero">
      <div class="hero_left">
        <span>Développeur Web</span>
        <h1 class="title">
          Je suis Nath Drnt, une jeune développeuse en herbe
        </h1>
        <p>Bienvenue sur mon Portfolio</p>
      </div>

      <div class="hero_right">
        <div class="hero-img">
          <img src="../assets/images/avatar.png" alt="Avatar Nath" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
span {
  text-transform: uppercase;
}
.hero {
  background-color: rgba(182, 121, 182, 0.849);
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 80px 20px 90px 0;
}
.hero .title {
  font-size: 40px;
  text-shadow: 2px 2px 4px white;
  font-weight: bold;
  line-height: 1.5;
}
.hero_left {
  animation-duration: 1s;
  animation-name: slideInLeft;
  padding-left: 70px;
}
.hero_right {
  animation-duration: 1s;
  animation-name: slideInRight;
  padding-right: 80px;
  padding-left: 90px;
}
.hero-img img {
  width: 200%;
  border-radius: 50%;
  background-color: white;
}

@media screen and (min-width: 750px) {
  .hero-img img {
    width: 400px;
    height: 400px;
  }
}

/* Effet d'animation */
@keyframes slideInLeft {
  from {
    transform: translateX(-110%);
  }
  to {
    transform: translateX(0%);
  }
}

@keyframes slideInRight {
  from {
    transform: translateX(110%);
  }
  to {
    transform: translateX(0%);
  }
}
</style>

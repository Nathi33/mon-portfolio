<template>
  <footer>
    <div class="footer">
      <figure class="logo">
        <!--L'attribut "rel" sert à améliorer la  sécurité des liens externes en protégeant contre  certaines attaques-->
        <a
          target="_blank"
          href="https://fr.linkedin.com/"
          rel="noopener noreferrer"
          ><img
            src="../assets/images/logo-linked.png"
            alt="Lien vers le profil LinkedIn de Nath Drnt"
          />
        </a>
        <a
          target="_blank"
          href="https://twitter.com/?lang=fr"
          rel="noopener noreferrer"
          ><img
            src="../assets/images/logo-twitter.png"
            alt="Lien vers le profil Twitter de Nath Drnt"
          />
        </a>
        <a
          target="_blank"
          href="https://instagram.com/"
          rel="noopener noreferrer"
          ><img
            src="../assets/images/instagram.png"
            alt="Lien vers le profil Instagram de Nath Drnt"
        /></a>
        <a
          target="_blank"
          href="https://facebook.com/"
          rel="noopener noreferrer"
          ><img
            src="../assets/images/facebook.png"
            alt="Lien vers le profil Facebook de Nath Drnt"
          />
        </a>
        <a target="_blank" href="https://github.com/" rel="noopener noreferrer"
          ><img
            src="../assets/images/logo-git.png"
            alt="Lien vers le profil GitHub de Nath Drnt"
          />
        </a>
      </figure>
      <small
        >Dernière mise à jour le
        <time datetime="2024-02-25">25 février 2024</time></small
      >
    </div>
  </footer>
</template>

<script setup></script>

<style scoped>
.footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 10px;
  padding-top: 20px;
  text-align: center;
}

.logo {
  display: flex;
  gap: 10px;
  justify-content: center;
}

.logo img {
  width: 30px;
  height: 30px;
  object-fit: cover;
  padding-left: 5px;
  padding-bottom: 5px;
}

.logo img:hover {
  opacity: 0.5;
}
</style>

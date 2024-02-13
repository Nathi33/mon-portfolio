<template>
  <footer>
    <div class="footer">
      <div class="logo">
        <a target="_blank" href="https://fr.linkedin.com/"
          ><img src="../assets/images/logo-linked.png" alt="Logo Linkedin" />
        </a>
        <a target="_blank" href="https://twitter.com/?lang=fr"
          ><img src="../assets/images/logo-twitter.png" alt="Logo Twitter" />
        </a>
        <a target="_blank" href="https://github.com/"
          ><img src="../assets/images/logo-git.png" alt="Logo GitHub" />
        </a>
      </div>
      <small
        >Dernière mise à jour le
        <time datetime="2024-02-13">13 février 2024</time></small
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
}

.logo img {
  width: 30px; /*40px*/
  height: 30px; /*40px*/
  object-fit: cover;
  padding-left: 5px; /*10px*/
  padding-bottom: 5px; /*10px*/
}

.logo img:hover {
  opacity: 0.5;
}
</style>

<template>
  <footer class="footer-nav">
      <a href="#" class="nav-item text-center">
        <img src="./../assets/images/home_icon_active.webp" alt="Home" class="footer-icon">
        <p>Inicio</p>
      </a>
      <a href="#" class="nav-item text-center">
        <img src="./../assets/images/promotion_icon.webp" alt="Home" class="footer-icon">
        <p>Eventos</p>
      </a>
      <a href="#" class="nav-item text-center">
        <img src="./../assets/images/topUp_icon.webp" alt="Home" class="footer-icon">
        <p>Depósito</p>
      </a>
      <a href="#" class="nav-item text-center">
        <img src="./../assets/images/chat_icon.webp" alt="Home" class="footer-icon">
        <p>Suporte</p>
      </a>
      <a href="#" class="nav-item text-center">
        <img src="./../assets/images/mine_icon.webp" alt="Home" class="footer-icon">
        <p>Perfil</p>
      </a>
  </footer>
</template>

<style scoped>
.footer-nav {
  background-color: #014789;
  color: white;
  display: flex;
  justify-content: space-around;
  padding: 11px 25px 10px 10px;
  position: fixed;
  bottom: 0;
  width: 100%;
  height: calc(min(100vw,490px) / 750 * 122);
  max-width: 490px;
  z-index: 1;
}

.nav-item {
  margin-left: calc(min(100vw,490px)*.032);
  display: flex;
  flex-direction: column;
  align-items: center;
  width: calc(min(100vw, 490px) / 750* 110);
  height: calc(min(100vw, 490px)* .112);
  margin-top: calc(min(100vw, 490px)* .024);
  justify-content: space-between;
  cursor: pointer;
}

.footer-icon {
  width: calc(min(100vw, 490px)* .065);
  height: calc(min(100vw, 490px)* .066);
}

.nav-item p {
  font-size: calc(min(100vw,490px) / 750 * 22);
  font-family: Arial, Helvetica, sans-serif;
  color: #fcfcfc;
}
</style>

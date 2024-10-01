<template>
  <header class="bg-custom-blue p-4 flex justify-between w-full">
    <!-- Menu Icon (left-aligned) -->
    <img
      src="./../assets/images/header_menu_icon.webp"
      alt="Menu Icon"
      class="w-6 h-6 md:w-8 md:h-8 menu-icon"
      @click="toggleMenu"
      :class="{ rotated: isMenuOpen }"
    />

    <!-- Left Logo -->
    <div class="flex flex-1">
      <img src="./../assets/images/logopixpg.webp" alt="PixPG Logo" class="mx-auto w-24 md:w-28">
    </div>

    <!-- Buttons (right-aligned) -->
    <nav class="flex space-x-2">
      <button class="login-btn">Login</button>
      <button class="register-btn">Registro</button>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
  data() {
    return {
      isMenuOpen: false, // Track the state of the side menu
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
      this.$emit('toggleSideMenu');
    },
  },
};
</script>

<style scoped>
/* Header background */
.bg-custom-blue {
  background-color: #014789;
  height: 4rem;
  display: flex;
  align-items: center;
  justify-content: left;
}

/* Menu Icon */
.w-6 {
  width: 2rem;
  height: auto;
  margin-left: 1rem;
}

.md\:w-8 {
  width: 2.2rem;
  height: 2.3rem;
}

/* Rotation animation for the menu icon */
.menu-icon {
  transition: transform 0.3s ease-in-out;
  cursor: pointer;
}

.rotated {
  transform: rotate(-180deg); /* Rotate an additional 180 degrees on click */
}

/* No space between header and body */
.w-24 {
  width: 10rem;
  height: auto;
}

.md\:w-28 {
  width: 7rem;
}

.mx-auto {
  margin-left: 0.7rem;
  margin-top: 0.2rem;
  width: 9.3rem;
  height: auto;
}

/* Button Styles */
.login-btn,
.register-btn {
  border: 1px solid #FFFCD2;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.25);
  color: #fffcd2;
  background-color: inherit;
  font-weight: 400;
  width: calc(min(100vw, 490px) / 750 * 140);
  height: calc(min(100vw, 490px) * 0.072);
  font-size: calc(min(100vw, 490px) * 0.032);
  border-radius: calc(min(100vw, 490px) * 0.016);
  margin-left: calc(min(100vw, 490px) * 0.016);
  padding: 0.5rem 1rem;
}

.login-btn {
  margin-left: 4.5rem;
  background-color: #fffcd2;
  color: #014789;
}

.register-btn {
  margin-left: 0.5rem;
}
</style>

<template>
  <div class="container">
    <div 
      class="main-body" 
      ref="mainBody" 
      @scroll="handleScroll"
    >
      <!-- Top Banner -->
      <Banner ref="banner"/>

      <!-- Notice Section with Sound Icon -->
      <div class="notice-section">
        <img src="./../assets/images/furlaBlue_voice_icon.webp" alt="Sound Icon" class="sound-icon" />
        <div class="notice-box">
          <!-- Notice content can be added here -->
        </div>
        <div class="notice-text">
          <span>
            Bem-vindo ao pixpg.app
            ~ 1.Três bônus grátis no seu primeiro depósito até 20 por cento
            ~ 2.Convide amigos e ganhe até 10 cada convidado!
          </span>
        </div>
        <div class="notice-mail-icon">
          <svg fill="#fffcd2" width="26px" height="26px" viewBox="0 0 1920 1920" xmlns="http://www.w3.org/2000/svg">
            <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
            <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
            <g id="SVGRepo_iconCarrier">
              <path d="M0 1694.235h1920V226H0v1468.235ZM112.941 376.664V338.94H1807.06v37.723L960 1111.233l-847.059-734.57ZM1807.06 526.198v950.513l-351.134-438.89-88.32 70.475 378.353 472.998H174.042l378.353-472.998-88.32-70.475-351.134 438.89V526.198L960 1260.768l847.059-734.57Z" fill-rule="evenodd"></path>
            </g>
          </svg>
        </div>
      </div>

      <!-- Jackpot Section -->
      <div class="jackpot-section">
        <img src="./../assets/images/JACKPOT-PIXPG-ezgif.com-video-to-webp-converter.webp" alt="Jackpot" class="jackpot-img" />
      </div>

      <!-- Menu Section -->
      <div 
        class="menu-section" 
        :class="{ 'fixed': isFixed }" 
        :style="{ width: isFixed ? fixedWidth + 'px' : 'auto', top: isFixed ? '64px' : 'auto' }" 
        ref="menuSection"
      >
        <div class="menu-item">
          <img src="./../assets/images/download.png" alt="Popular" class="menu-item-icon" />
          <div class="menu-item-text">Popular</div>
        </div>

        <div class="menu-item">
          <img src="./../assets/images/PG.webp" alt="PG Slots" class="menu-item-icon" />
          <div class="menu-item-text">PG Slots</div>
        </div>

        <div class="menu-item">
          <img src="./../assets/images/PP.webp" alt="PP Slots" class="menu-item-icon" />
          <div class="menu-item-text">PP Slots</div>
        </div>

        <div class="menu-item">
          <svg class="_icons_370vb_582 _defaultCss_au2i1_3" width="40" height="31" viewBox="0 0 40 31" fill="none" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M7.22189 10.3569C6.82375 9.32662 7.33624 8.16862 8.36655 7.77048L19.7931 3.35498C20.8234 2.95684 21.9814 3.46932 22.3796 4.49964L28.6178 20.643C29.0159 21.6734 28.5034 22.8314 27.4731 23.2295L16.0466 27.645C15.0162 28.0431 13.8582 27.5307 13.4601 26.5003L7.22189 10.3569ZM19.8449 18.4708C22.7944 18.8523 24.1131 17.3437 23.1882 14.9505C22.1928 12.3747 16.3269 11.0669 16.3269 11.0669C16.3269 11.0669 12.8651 15.9796 13.8606 18.5553C14.7744 20.9199 17.0515 21.0476 18.7127 18.962L18.977 20.2421C19.0937 20.8072 18.7848 21.3739 18.2465 21.5819L18.4267 22.0483L22.1578 20.6063L21.9776 20.1399C21.4393 20.348 20.8295 20.1364 20.5359 19.6396L19.8449 18.4708ZM10.6879 9.5033C10.8966 10.0434 10.599 10.3839 9.93333 10.2978L10.0893 10.5616C10.1556 10.6737 10.2932 10.7214 10.4146 10.6745L10.4553 10.7797L9.61329 11.1051L9.57261 10.9999C9.69409 10.9529 9.76382 10.8251 9.73748 10.6975L9.67782 10.4086C9.30292 10.8793 8.78902 10.8505 8.58278 10.3169C8.35813 9.73555 9.1394 8.62683 9.1394 8.62683C9.1394 8.62683 10.4632 8.92199 10.6879 9.5033ZM26.9333 21.2978C27.599 21.3839 27.8966 21.0434 27.6879 20.5033C27.4632 19.922 26.1394 19.6268 26.1394 19.6268C26.1394 19.6268 25.3581 20.7355 25.5828 21.3169C25.789 21.8505 26.3029 21.8793 26.6778 21.4086L26.7375 21.6975C26.7638 21.8251 26.6941 21.9529 26.5726 21.9999L26.6133 22.1051L27.4553 21.7797L27.4146 21.6745C27.2932 21.7214 27.1556 21.6737 27.0893 21.5616L26.9333 21.2978Z" fill-opacity="0.6"></path><path d="M30.9129 24.5712H26.6604L28.6721 23.7938C29.8214 23.3497 30.3931 22.0579 29.949 20.9086L27.8296 15.4239C28.8218 14.3681 29.6629 13.1391 29.6629 12.0066C29.6629 9.56041 28.0505 8.59946 25.6351 9.74498L23.1309 3.26443H30.9129C32.0174 3.26443 32.9129 4.15987 32.9129 5.26443V22.5712C32.9129 23.6758 32.0174 24.5712 30.9129 24.5712Z" fill-opacity="0.6"></path></svg>

          <div class="menu-item-text">Evolution</div>
        </div>

        <div class="menu-item">
          
          <svg class="_icon_370vb_562 _icons_370vb_582 _defaultCss_1284p_3" width="40" height="30" viewBox="0 0 40 30" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M14.0826 6.92748H21.1041L23.1743 4.85726C23.9121 4.11941 23.2256 2.87579 22.208 3.10705C21.8651 3.18497 21.5061 3.08443 21.2535 2.83977L20.5071 2.11662C20.0446 1.66862 19.3152 1.65233 18.8332 2.07923L18.3485 2.50856C17.8823 2.92149 17.1812 2.92149 16.715 2.50855L16.2734 2.11744C15.7739 1.67501 15.0129 1.71075 14.557 2.19804L14.0098 2.78302C13.7491 3.06169 13.3617 3.18377 12.9883 3.10489C11.9126 2.87762 11.215 4.20513 12.0124 4.96214L14.0826 6.92748Z" fill="white" fill-opacity="0.6"></path>
            <path d="M7 17.43C7 13.6364 9.7726 9.53293 13.7001 7.78981H21.6723C23.4483 8.57805 24.9882 9.84893 26.1423 11.3556C23.6991 11.7239 21.9061 12.9395 21.9061 14.3824C21.9061 14.4031 21.9065 14.4237 21.9072 14.4443H21.9061V17.8958C21.7836 17.8917 21.6601 17.8896 21.5357 17.8896C20.3775 17.8896 19.2971 18.07 18.385 18.3817V17.8876C18.6696 17.8397 18.9245 17.7425 19.1499 17.596C19.3781 17.4467 19.5584 17.2523 19.6908 17.0128C19.8232 16.7706 19.8894 16.4874 19.8894 16.1635C19.8894 15.8536 19.8359 15.5902 19.7288 15.3733C19.6246 15.1563 19.4865 14.9761 19.3147 14.8324C19.1457 14.6859 18.9583 14.5648 18.7527 14.469C18.5498 14.3704 18.3484 14.2844 18.1484 14.2112C17.9568 14.1408 17.7808 14.0675 17.6202 13.9915C17.4596 13.9154 17.3314 13.8267 17.2356 13.7252C17.1399 13.6238 17.092 13.4985 17.092 13.3492C17.092 13.1632 17.1568 13.0181 17.2863 12.9139C17.4188 12.8097 17.599 12.7576 17.8272 12.7576C18.0695 12.7576 18.2667 12.8181 18.4188 12.9393C18.571 13.0576 18.6808 13.1998 18.7484 13.3661L19.6527 13.0618C19.5682 12.7745 19.4203 12.5237 19.209 12.3096C18.9978 12.0927 18.7231 11.9462 18.385 11.8702V11.1856H17.4047V11.8617C16.9736 11.9378 16.6426 12.1167 16.4116 12.3984C16.1834 12.6773 16.0693 12.9942 16.0693 13.3492C16.0693 13.6281 16.1172 13.8647 16.213 14.0591C16.3116 14.2506 16.4412 14.4126 16.6018 14.545C16.7624 14.6746 16.9398 14.7859 17.1342 14.8789C17.3286 14.969 17.523 15.0507 17.7174 15.124C17.9174 15.2 18.1033 15.2831 18.2752 15.3733C18.4498 15.4634 18.5907 15.5719 18.6977 15.6986C18.8048 15.8254 18.8583 15.9832 18.8583 16.1719C18.8583 16.4339 18.7766 16.6353 18.6132 16.7762C18.4498 16.9142 18.2329 16.9833 17.9625 16.9833C17.6976 16.9833 17.461 16.9002 17.2525 16.7339C17.0469 16.5649 16.8863 16.3494 16.7708 16.0874L15.8496 16.4255C15.9736 16.7917 16.1679 17.1016 16.4328 17.3551C16.6976 17.6087 17.0215 17.7805 17.4047 17.8707V18.6228H17.7705C16.4588 19.2103 15.6229 20.0985 15.6229 21.0924C15.6229 21.1344 15.6244 21.1762 15.6273 21.2178H15.6229V25.457C10.7084 24.8051 7 21.8174 7 17.43Z" fill="white" fill-opacity="0.6"></path>
            <path d="M21.4471 24.461C24.2559 24.461 26.5329 23.2373 26.5329 21.7278C26.5329 20.2182 24.2559 18.9945 21.4471 18.9945C18.6383 18.9945 16.3613 20.2182 16.3613 21.7278C16.3613 23.2373 18.6383 24.461 21.4471 24.461Z" fill="white" fill-opacity="0.6"></path>
            <path d="M26.5328 22.4482C26.5036 23.9442 24.2377 25.1521 21.4471 25.1521C18.6565 25.1521 16.3909 23.9442 16.3616 22.4482L16.3613 22.4189V22.0157L16.3612 23.6787C16.3905 25.1747 18.6564 26.3826 21.447 26.3826C24.2376 26.3826 26.5033 25.1747 26.5325 23.6787L26.5328 23.6493V22.4482Z" fill="white" fill-opacity="0.6"></path>
            <path d="M26.5328 24.2956C26.5035 25.7917 24.2376 26.9996 21.447 26.9996C18.6564 26.9996 16.3908 25.7917 16.3615 24.2956L16.3612 24.2663V23.8632L16.3612 25.5262C16.3904 27.0222 18.6564 28.2302 21.447 28.2302C24.2376 28.2302 26.5032 27.0222 26.5325 25.5262L26.5328 25.4969V24.2956Z" fill="white" fill-opacity="0.6"></path>
            <path d="M27.9139 17.5947C30.7227 17.5947 32.9997 16.3709 32.9997 14.8614C32.9997 13.3519 30.7227 12.1281 27.9139 12.1281C25.1051 12.1281 22.8281 13.3519 22.8281 14.8614C22.8281 16.3709 25.1051 17.5947 27.9139 17.5947Z" fill="white" fill-opacity="0.6"></path>
            <path d="M32.9997 15.5818V15.1493L32.9998 16.8123C32.9705 18.3083 30.7046 19.5162 27.914 19.5162C27.4527 19.5162 27.0057 19.4832 26.5808 19.4213C25.8604 18.7846 24.7407 18.2949 23.4106 18.0542C23.0466 17.6825 22.8372 17.2603 22.8285 16.8123L22.8282 16.7829V15.5818C22.8574 17.0779 25.1233 18.2858 27.9139 18.2858C30.7045 18.2858 32.9704 17.0779 32.9997 15.5818Z" fill="white" fill-opacity="0.6"></path>
            <path d="M22.8284 17.4295C22.8321 17.6186 22.8715 17.8031 22.9432 17.9811C22.905 17.9761 22.8667 17.9712 22.8282 17.9666L22.8284 17.4295Z" fill="white" fill-opacity="0.6"></path>
            <path d="M27.4487 21.218V21.3527C27.6019 21.3601 27.7571 21.3639 27.914 21.3639C30.7046 21.3639 32.9702 20.156 32.9995 18.66L32.9998 18.6307V16.997L32.9997 17.4295C32.9704 18.9255 30.7045 20.1334 27.9139 20.1334C27.6583 20.1334 27.407 20.1233 27.1615 20.1037C27.3479 20.4152 27.4487 20.7475 27.4487 21.0926C27.4487 21.1346 27.4472 21.1764 27.4443 21.218H27.4487Z" fill="white" fill-opacity="0.6"></path>
            <path d="M27.4487 21.9696V23.2C27.6019 23.2075 27.7572 23.2113 27.914 23.2113C30.7046 23.2113 32.9703 22.0034 32.9995 20.5073L32.9998 20.478V18.8444L32.9998 19.277C32.9705 20.773 30.7046 21.9809 27.914 21.9809C27.7571 21.9809 27.6019 21.9771 27.4487 21.9696Z" fill="white" fill-opacity="0.6"></path>
            <path d="M27.4487 23.8174V25.0478C27.6019 25.0553 27.7572 25.0591 27.914 25.0591C30.7046 25.0591 32.9703 23.8512 32.9995 22.3552L32.9998 22.3259V20.6922L32.9998 21.1247C32.9705 22.6207 30.7046 23.8287 27.914 23.8287C27.7571 23.8287 27.6019 23.8248 27.4487 23.8174Z" fill="white" fill-opacity="0.6"></path>
        </svg>

          <div class="menu-item-text">Convidar</div>
        </div>
      </div>

      <!-- Game Section -->
      <GameSection />

      <div class="bottom"></div>
    </div>
  </div>
</template>

<script>
import GameSection from './GameSection.vue';
import Banner from './Banner.vue';

export default {
  name: 'MainBody',
  components: {
    GameSection,
    Banner,
  },
  data() {
    return {
      isFixed: false, 
      menuTop: 0,
      bannerHeight: 0,
      fixedWidth: 0,
    };
  },
  methods: {
  handleScroll() {
    const menuSection = this.$refs.menuSection;
    const mainBody = this.$refs.mainBody;
    const banner = this.$refs.banner;

    if (menuSection && mainBody && banner) {
      const scrollTop = mainBody.scrollTop;
      
      // Fix the menu section just after the banner
      if (scrollTop >= 360) {
        this.isFixed = true;
        this.fixedWidth = menuSection.offsetWidth;
        this.bannerHeight = 360;
      } else {
        this.isFixed = false;
      }
    }
  },
},

  mounted() {
    const menuSection = this.$refs.menuSection;
    const banner = this.$refs.banner;
    
    if (menuSection) {
      this.menuTop = menuSection.offsetTop; // Set initial top position of the menu section
      this.bannerHeight = banner.$el.offsetHeight; // Store the height of the banner initially
    }
  }
};
</script>

<style scoped>
/* Global styles */
html, body {
  height: 100%;
  margin: 0;
}

/* Container to hold header, main body, and footer */
.container {
  display: flex;
  flex-direction: column;
  height: 100vh; /* Full height of the viewport */
}

/* Main body styles */
.main-body {
  background-color: #8eaae1;
  background-image: url('./../assets/images/bg_pattern_tile.png');
  background-size: 10%;
  background-repeat: repeat;
  background-position: center bottom;
  background-attachment: fixed;
  flex: 1; /* Take up remaining space */
  padding: 0;
  overflow-y: auto; /* Enable vertical scrolling only */
}

/* Hide scrollbar for Webkit browsers (Chrome, Safari) */
.main-body::-webkit-scrollbar {
  display: none; /* Hide scrollbar */
}

/* Hide scrollbar for Firefox */
.main-body {
  scrollbar-width: none; /* Hide scrollbar */
}

/* Footer styles */
.footer {
  background-color: #014789; /* Adjust as needed */
  color: white;
  padding: 1rem; /* Adjust as needed */
}

/* Notice Section */
.notice-section {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #014789;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  padding: 0 5%;
  height: calc(min(100vw, 490px) * 0.08);
  margin-top: 0.9rem;
  box-sizing: border-box;
}

.sound-icon {
  width: calc(min(100vw, 490px) * 0.035);
  margin-left: -0.5rem;
}

.notice-box {
  flex: 1;
  text-align: center;
  color: rgba(255, 255, 255, 0.88);
  font-size: calc(min(100vw, 490px) / 750 * 22);
  font-weight: 700;
  margin-right: calc(min(100vw, 490px) * 0.016);
  font-family: Arial, Helvetica, sans-serif;
}

/* Notice text that scrolls */
.notice-text {
  color: white;
  white-space: nowrap; 
  text-align: center;
  font-weight: bold;
  font-size: calc(min(100vw, 490px) * 0.032);
  overflow: hidden; 
  width: 100%; 
  position: relative;
}

.notice-mail-icon {
  margin-right: -0.4rem;
  margin-top: 0.5rem;
  margin-left: 0.6rem;
}

.notice-text span {
  display: inline-block;
  padding-left: 100%; 
  animation: scroll-left 40s linear infinite;
}

@keyframes scroll-left {
  0% {
    transform: translateX(100%); 
  }
  100% {
    transform: translateX(-100%); 
  }
}

/* Jackpot Section */
.jackpot-section {
  text-align: center;
  margin: 0; 
  padding: 0; 
}

.jackpot-img {
  width: 100%;
  max-width: 100vw;
  display: block;
  margin: 0; 
}

/* Menu Section */
.menu-section {
  height: calc(min(100vw, 490px) * 0.16);
  width: 100%;
  background-color: #014789;
  display: flex;
  justify-content: space-evenly;
  padding: 1rem 3rem;
  transition: top 0.3s ease;
}

.fixed {
  position: fixed;
  top: 0;
  z-index: 1000;
}

.menu-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: calc(min(100vw, 490px) * 0.16);
  cursor: pointer;
}

.menu-item-icon {
  width: 35px;
  height: auto;
}

.menu-item-text {
  color: rgba(255, 255, 255, 0.6);
  font-weight: 700;
  font-size: calc(min(100vw, 490px) / 750 * 22);
  font-family: Arial, Helvetica, sans-serif;
  margin-top: auto;
}


/* Game Section */
.game-section {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 1rem;
}

.game-box {
  width: 100%;
  margin-left: calc(min(100vw, 490px) * 0.032);
}

.game-box-title {
  color: white;
  font-size: calc(min(100vw, 490px) * 0.032);
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
}

.games {
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-start;
  margin-top: 1rem;
}

.game {
  width: calc(min(100vw, 490px) / 750 * 218);
  height: calc(min(100vw, 490px) / 750 * 290);
  margin-right: calc(min(100vw, 490px) * 0.032);
  margin-bottom: calc(min(100vw, 490px) * 0.032);
  background-color: #0d273f;
  border-radius: 0.5rem;
  position: relative;
}

.game-img {
  width: 100%;
  height: 100%;
  border-radius: 0.5rem;
}

.game-title-box {
  width: 100%;
  height: 25%;
  font-size: calc(min(100vw, 490px) / 750 * 22);
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  position: absolute;
  bottom: 0;
}

.game-title-text {
  color: white;
  font-size: calc(min(100vw, 490px) / 750 * 28);
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 400;
}

.game-platform-text {
  color: white;
  font-size: calc(min(100vw, 490px) / 750 * 20);
  font-family: Arial, Helvetica, sans-serif;
  margin-top: 0.6rem;
  font-weight: 600;
}

.bottom {
  height: 100px;
}
</style>

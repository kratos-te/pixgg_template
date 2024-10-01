<template>
    <div class="game-section">
      <!-- Loop through the game sections array and display each section -->
      <div v-for="(section, sectionIndex) in gameSections" :key="sectionIndex" class="game-box">
        <!-- Section title -->
         <div class="game-box-title-box">
              <img :src="section.icon" :alt="section.title" class="game-box-title-icon">
            <div class="game-box-title">{{ section.title }}</div>
         </div>
        <div class="games">
          <!-- Loop through the games array for each section and display each game -->
          <div v-for="(game, gameIndex) in section.games" :key="gameIndex" class="game">
            <img :src="game.image" :alt="game.title" class="game-img">
            <div class="game-title-box">
              <div class="game-title-text">{{ game.title }}</div>
              <div class="game-platform-text">{{ game.platform }}</div>
            </div>
            <img class="game-collect-icon" src="./../assets/images/collect.webp" alt="Collect Icon">
          </div>
        </div>
        <div class="more-games-box">
          <div class="more-games-btn">+ Carregar mais</div>
          <svg class="more-games-icon" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M9.14014 8.63572L3.69287 3.6582L2.80859 4.4657L7.37091 8.6353L2.80859 12.7999L3.69321 13.6082L9.14014 8.63572ZM13.4038 8.63572L7.95654 3.6582L7.07227 4.4657L11.6346 8.6353L7.07227 12.7999L7.95688 13.6082L13.4038 8.63572Z" fill="#FFDC82"></path>
          </svg>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import PGSlotImage from '@/assets/images/PG-SLOT-093.png.webp';
  import MGSlotImage from '@/assets/images/PG-SLOT-093.png.webp';
  import SectionIcon from '@/assets/images/download.png';
  
  export default {
    name: 'GameSection',
    data() {
      return {
        gameSections: [
          {
            title: 'PG Slots',
            icon: SectionIcon,
            games: [
              {
                title: 'PG Slots 1',
                platform: 'PG',
                image: PGSlotImage,
              },
              {
                title: 'PG Slots 2',
                platform: 'PG',
                image: PGSlotImage,
              },
              {
                title: 'PG Slots 3',
                platform: 'PG',
                image: PGSlotImage,
              },
              {
                title: 'PG Slots 4',
                platform: 'PG',
                image: PGSlotImage,
              },
            ],
          },
          {
            title: 'MG Slots',
            icon: SectionIcon,
            games: [
              {
                title: 'MG Slots 1',
                platform: 'MG',
                image: MGSlotImage,
              },
              {
                title: 'MG Slots 2',
                platform: 'MG',
                image: MGSlotImage,
              },
              {
                title: 'MG Slots 3',
                platform: 'MG',
                image: MGSlotImage,
              },
              {
                title: 'MG Slots 4',
                platform: 'MG',
                image: MGSlotImage,
              },
            ],
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .game-section {
    width: 100%;
    grid-column: span 4;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 1rem;
  }
  
  .game-box {
    margin-left: calc(min(100vw, 490px) * 0.032);
    margin-bottom: 2rem; /* Adds space between sections */
  }

  .game-box-title-box {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
  }

  .game-box-title-icon {
    width: calc(min(100vw, 490px) / 25);
  }
  
  .game-box-title {
    color: white;
    font-size: calc(min(100vw, 490px) * 0.032);
    font-weight: bold;
    font-family: Arial, Helvetica, sans-serif;
    margin-left: 0.5rem;
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
    cursor: pointer;
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

  .game-collect-icon {
    top: calc(min(100vw, 490px) / 750* 8);
    right: calc(min(100vw, 490px) / 750* 8);
    width: calc(min(100vw, 490px) / 750* 40);
    height: calc(min(100vw, 490px) / 750* 40);
    position: absolute;
  }
  
  .more-games-box {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: 1rem;
    cursor: pointer;
  }
  
  .more-games-btn {
    color: white;
    font-size: calc(min(100vw, 490px) / 750 * 22);
    font-family: Arial, Helvetica, sans-serif;
    cursor: pointer;
  }

  .more-games-icon {
    width: calc(min(100vw, 490px)* .032);
    margin-left: calc(min(100vw, 490px)* .016);
    transform: rotate(90deg);
  }
  </style>
  
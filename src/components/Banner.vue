<template>
    <div class="carousel-container">
      <div class="carousel-track" :style="trackStyle">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image"
          alt="Banner Image"
          class="carousel-image"
        />
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ImageCarousel',
    data() {
      return {
        images: [
          'https://pixpg.app/img/WEB%20BANNER%20-%20PIX%20PG2.webp',
          'https://pixpg.app/img/WEB%20BANNER%20-%20PIX%20PG3.webp',
          'https://pixpg.app/img/WEB%20BANNER%20-%20PIX%20PG1.webp'
        ],
        currentIndex: 0,
      };
    },
    computed: {
      trackStyle() {
        return {
          transform: `translateX(-${this.currentIndex * 580}px)`, // Move by 580px for each image
          width: `${this.images.length * 580}px`, // Set width dynamically based on the number of images
          transition: 'transform 0.5s ease-in-out' // Smooth transition
        };
      }
    },
    mounted() {
      this.startCarousel();
    },
    methods: {
      startCarousel() {
        setInterval(() => {
          this.currentIndex = (this.currentIndex + 1) % this.images.length;
        }, 5000); // Move every 5 seconds
      }
    }
  };
  </script>
  
  <style scoped>
  .carousel-container {
    width: 480px; /* Fixed width for the container */
    overflow: hidden; /* Hide the overflowing images */
    position: relative;
    border-radius: .6rem;
    margin-left: 5px; /* Add left margin */
    margin-top: 8px; /* Add top margin */
    cursor: pointer;
  }
  
  .carousel-track {
    display: flex;
  }
  
  .carousel-image {
    width: 580px; /* Fixed width for each image */
    height: 9.4rem;
    flex-shrink: 0; /* Prevent images from shrinking */
  }
  </style>
  
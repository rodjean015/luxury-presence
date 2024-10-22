<template>
    <div class="real-estate-section">
      <h4 class="center-text">
        <strong>
          Intentional Layout
        </strong>
        <p>
          Review all documents and sign in the comfort of your home or anywhere.
          Stay up to date on all marketing activities, review materials, photos, etc. in real time.
          Meet with us face to face on our Gotomeeting.com platform to go over and discuss the events of the week.
          You have your own email assigned just for you and your common space to quickly write a note, or quickly send a video message to us for fast communication using our Bomb bomb video messaging system.
        </p>
      </h4>
      <br />
  
      <!-- Real Estate Success Cards -->
      <div class="services-row">
        <div class="service-item" v-for="(card, index) in cards" :key="index">
          <div class="thumbnail slideanim">
            <div class="image-container">
              <img :src="card.imgSrc" :alt="card.imgAlt" class="service-img" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cards: [
          {
            imgSrc: 'src/img/pic4.png',
            imgAlt: 'Real Estate Success Image 1',
          },
          {
            imgSrc: 'src/img/pic5.png',
            imgAlt: 'Real Estate Success Image 2',
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .real-estate-section {
    margin-top: 20px;
  }
  
  .center-text {
    text-align: center;
    font-size: 2rem;
    line-height: 1.8;
    margin: 0 auto;
    max-width: 800px;
  }
  
  .center-text p {
    font-size: 1.1rem;
    line-height: 1.6;
    margin-top: 10px;
  }
  
  .services-row {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  
  .service-item {
    flex: 1 1 calc(33.33% - 20px);
    margin: 10px;
  }
  
  .thumbnail {
    border: none;
    padding: 10px;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    overflow: hidden;
    position: relative;
  }
  
  .image-container {
    position: relative;
    overflow: hidden;
  }
  
  .service-img {
    display: block;
    max-width: 80%;
    height: auto;
    margin: 0 auto;
    transition: transform 0.5s ease; /* Smooth transition for zoom and rotation */
  }
  
  .service-img:hover {
    transform: scale(1.2); /* Zoom in and rotate 10 degrees clockwise */
  }
  
  .slideanim {
    animation: fadeInUp 1s ease-in-out;
  }
  
  @keyframes fadeInUp {
    0% {
      opacity: 0;
      transform: translateY(20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @media (max-width: 768px) {
    .service-item {
      flex: 1 1 100%;
    }
  
    .service-img {
      max-width: 60%;
    }
  }
  </style>
  
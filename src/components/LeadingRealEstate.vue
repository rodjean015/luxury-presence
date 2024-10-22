<template>
    <div class="real-estate-section">
      <h4 class="center-text">
        <strong>
            Leading Real Estate Companies of The World® & Luxury Portfolio International
        </strong>
      </h4>
      <br />
  
      <!-- Real Estate Success Cards -->
      <div class="row services-row">
        <div class="service-item" v-for="(card, index) in cards" :key="index">
          <div class="thumbnail slideanim">
            <div class="image-container">
              <img :src="card.imgSrc" :alt="card.imgAlt" class="service-img" />
              <div class="overlay">
                <div class="intro">
                  <p>{{ card.description }}</p>
                </div>
              </div>
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
            imgSrc: 'src/img/pic11.png',
            imgAlt: 'Real Estate Success Image 1',
            description:
                'JRockcliff is a founding member of Luxury Portfolio International®, the luxury division of Leading Real Estate Companies of the World®. With more than 500 member firms around the world, Our luxury listings are exposed to a vast global audience and reach potential buyers and investors in over 50 countries. Who’s Who in Luxury Real Estate Who’s Who in Luxury Real Estate is a global collection of luxury real estate brokers.'
            },
          {
            imgSrc: 'src/img/pic12.png',
            imgAlt: 'Real Estate Success Image 2',
            description:
              'Through our international affiliations, we have a strong presence in over 50 countries. Our luxury listings are sent to prominent international real estate sites, reaching over 70 million potential buyers and investors worldwide through our relationships with:',
          },
          {
            imgSrc: 'src/img/pic13.png',
            imgAlt: 'Real Estate Success Image 3',
            description:
              'Through our international affiliations, we have a strong presence in over 50 countries. Our luxury listings are sent to prominent international real estate sites, reaching over 70 million potential buyers and investors worldwide through our relationships with:',
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .real-estate-section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh; /* Ensure the section takes up full viewport height */
    text-align: center;
    padding: 20px;
  }
  
  .center-text {
    text-align: center;
    font-size: 1.5rem;
    line-height: 1.8;
    margin: 0 auto;
    max-width: 800px;
  }
  
  .services-row {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
  }
  
  .service-item {
    flex: 1 1 300px;
    margin: 10px;
    display: flex;
    justify-content: center;
  }
  
  .thumbnail {
    border: none;
    padding: 10px;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    overflow: hidden;
    position: relative;
    width: 400px; /* Set fixed width */
    height: 600px; /* Set fixed height */
  }
  
  .image-container {
    position: relative;
    width: 100%;
    height: 100%;
  }
  
  .service-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.7);
    color: white;
    opacity: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    transition: opacity 0.3s ease;
  }
  
  .thumbnail:hover .overlay {
    opacity: 1;
  }
  
  .intro p {
    margin: 10px 0;
    line-height: 1.6;
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
      max-width: 100%;
    }
  }
  </style>

<template>
    <div class="real-estate-section">
      <h4 class="center-text">
        <strong>
          Decor Guidance and My Staging Experience
        </strong>
        <p>
          Unclutter and organize your home<br/>
          Neatly arrange drawers and cabinets<br/>
          Keep pets outdoors or off the premises<br/>
          Play soft music
        </p>
      </h4>
      <br />
  
      <!-- Real Estate Success Cards -->
      <div class="services-row">
        <div class="service-item" v-for="(card, index) in cards" :key="index">
          <div class="thumbnail slideanim">
            <div class="image-container">
              <img :src="card.imgSrc" :alt="card.imgAlt" class="service-img" />
              <!-- Removed overlay with text -->
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
            imgSrc: 'src/img/pic1.png',
            imgAlt: 'Real Estate Success Image 1',
          },
          {
            imgSrc: 'src/img/pic3.png',
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
    height: 100vh;
  }
  
  .center-text {
    text-align: center;
    font-size: 2rem;
    line-height: 1.8;
    margin: 0 auto;
    max-width: 800px;
  }
  
  .center-text p {
    font-size: 1.1rem; /* Smaller font size for <p> */
    line-height: 1.6; /* Adjust line height for readability */
    margin-top: 10px; /* Add some margin at the top for spacing */
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
    overflow: hidden; /* Ensure the zoomed image doesn't overflow */
  }
  
  .service-img {
    display: block;
    max-width: 80%;
    height: auto;
    margin: 0 auto;
    transition: transform 0.5s ease; /* Smooth transition for zoom effect */
  }
  
  .service-img:hover {
    transform: scale(1.1); /* Zoom in by 10% on hover */
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
  
<template>
    <div class="real-estate-section">
      <h4 class="center-text">
        <strong>
          The Bay Area remains one of the world's most sought-after regions to live in, and when looking to sell, it is vital that your home be marketed online to audiences locally, nationally, and internationally.
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
                  <p class="text-center"><strong>{{ card.title }}</strong></p>
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
            imgSrc: 'src/img/pic6.png',
            imgAlt: 'Real Estate Success Image 1',
            title: 'Over 33 Years of Real Estate Success',
            description:
              'We provide every one of our clients with a level of service they won’t find anywhere else. We give them what they need, often before they know they need it. In real estate, almost everything can be negotiated. When you choose Hansen Partners, experience is 100% nonnegotiable. And it’s an experience like no other.',
          },
          {
            imgSrc: 'src/img/pic7.png',
            imgAlt: 'Real Estate Success Image 2',
            title: 'We Want To Create An Unforgettable Experience For You.',
            description:
              'We combine data gained from your home’s Comparative Market Analysis with local market research to create a marketing plan designed to help you meet your selling goals. Successfully marketing a home in today’s real estate environment requires a firm with experience and flexibility. Hansen Partners provides both.',
          },
          {
            imgSrc: 'src/img/pic8.png',
            imgAlt: 'Real Estate Success Image 3',
            title: 'The Hansen Partners Communications Tablet',
            description:
              'We believe that transparency and guiding you and your family through the process is key to having the best experience. During these uncertain times, it is a good feeling to know you have someone with a proven track record you can count on. We will be here to handle your needs during the real estate process. Who you work with does matter!',
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
    text-align: center; /* Center the text */
    font-size: 1.5rem; /* Adjust font size to 1.5 rem (you can change this as needed) */
    line-height: 1.8; /* Improve readability */
    margin: 0 auto; /* Center the element horizontally */
    max-width: 800px; /* Set a maximum width for readability */
  }
  
  .services-row {
    display: flex; /* Use Flexbox for horizontal alignment */
    justify-content: space-around; /* Distribute items evenly */
    flex-wrap: wrap; /* Wrap items if the screen size is smaller */
  }
  
  .service-item {
    flex: 1 1 calc(33.33% - 20px); /* Each item takes up 1/3 of the row minus the margin */
    margin: 10px;
  }
  
  .thumbnail {
    border: none;
    padding: 10px;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    overflow: hidden; /* Ensure content doesn't spill out */
    position: relative; /* Position for overlay effect */
  }
  
  .image-container {
    position: relative;
  }
  
  .service-img {
    display: block;
    width: 100%;
    height: auto;
  }
  
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.7); /* Semi-transparent black overlay */
    color: white;
    opacity: 0; /* Hidden by default */
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    transition: opacity 0.3s ease; /* Smooth transition */
  }
  
  .thumbnail:hover .overlay {
    opacity: 1; /* Show the overlay on hover */
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
      flex: 1 1 100%; /* Make items stack vertically on smaller screens */
    }
  }
  </style>
  
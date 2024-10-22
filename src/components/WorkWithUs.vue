<template>
    <div>
      <!-- Jumbotron Section -->
      <div class="jumbotron text-center">
        <h1 class="slideanim">Work With Us</h1>
        <p class="slideanim">
          With decades of experience in luxurious Tri Valley real estate, our team is here to ensure that your dreams are a reality. Let us guide you through your home buying journey, contact us today!
        </p>
      </div>
  
      <!-- Content Section (Horizontally Centered) -->
      <div class="container content-section">
        <!-- Left Column: Text -->
        <div class="text-section">
          <h4>Julie Hansen Partnership</h4>
          <p>
            An elite group of the East Bay’s most talented and visionary real estate professionals believed buyers and sellers deserved more from their real estate company. More service. More resources. More integrity. More global reach. In a word, more of everything people should expect when they buy or sell their homes.
          </p>
        </div>
  
        <!-- Right Column: Image -->
        <div class="image-section">
          <img :src="imageSrc" alt="Julie Hansen Team" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "WorkWithUs",
    data() {
      return {
        imageSrc: "src/img/pic2.png", // This will hold the dynamic image path
      };
    },
    mounted() {
      // Load the image through JavaScript when the component is mounted
      this.loadImage();
    },
    methods: {
      loadImage() {
        // Load the image dynamically, here you can specify the path
        this.imageSrc = require("@/assets/img/pic2.png");
      },
    },
  };
  </script>
  
  <style scoped>
  /* Flexbox layout to center the content horizontally and vertically */
  .content-section {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center; /* Ensure the text is centered */
    flex-wrap: wrap; /* Wrap the content for responsiveness */
    padding: 20px;
    gap: 20px; /* Add spacing between elements */
  }
  
  /* Style for the text section to be centered */
  .text-section {
    flex: 1;
    text-align: center; /* Center the text content */
    margin: 10px;
    min-width: 300px; /* Ensures the layout is responsive on smaller screens */
  }
  .text-section h4 {
    font-size: 2rem;
  }
  
  .image-section {
    flex: 1;
    display: flex;
    justify-content: center; /* Center the image horizontally */
    align-items: center; /* Center the image vertically */
    margin: 10px;
  }
  
  /* Image styling for circular image */
  .image-section img {
    width: 200px; /* Set width of the image */
    height: 200px; /* Set height of the image */
    border-radius: 50%; /* Make the image circular */
    object-fit: cover; /* Ensure the image covers the area without distortion */
  }
  
  .jumbotron {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    }

    .jumbotron h1, .jumbotron p {
    margin: 0; /* Remove any default margins */
    }
    .jumbotron h1 {
        font-size: 3rem;
    }
    p {
      font-size: 1.1rem;
      line-height: 1.6; /* Reduce line height */
    }

  
  /* Add any additional styles needed */
  </style>
  
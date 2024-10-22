<template>
    <div class="content-container">
      <div class="col-md-6">
        <h1 class="text-center">Elevating Your Real Estate Success</h1>
        <p class="text-justify">
          Our commitment to excellence extends beyond property transactions, it's
          about curating experiences and crafting narratives that turn each
          property into a unique story waiting to be told. With this comprehensive
          marketing plan, we aim to not only maximize the visibility of your
          listings but to establish an enduring connection between your properties
          and the target audience.
        </p>
        <p class="text-justify">
          Join us as we delve into a meticulously crafted roadmap, encompassing
          innovative digital strategies, traditional marketing channels, and
          cutting-edge technologies, all designed to amplify your real estate
          success. Together, let's embark on a journey where every property becomes
          a beacon, guiding the right buyers and tenants to their next home or
          investment.
        </p>
      </div>
  
      <!-- Services Section -->
      <div class="services-section" id="services">
        <div class="services-row">
          <div class="service-item">
            <i class="fa-regular fa-envelope slideanim"></i>
            <h2>Responsive</h2>
            <p>I am always available via phone, text, or email.</p>
          </div>
          <div class="service-item">
            <i class="fa-regular fa-flag slideanim"></i>
            <h2>Syndication</h2>
            <p>I market your property locally, nationally, and internationally.</p>
          </div>
          <div class="service-item">
            <i class="fa-solid fa-map-pin slideanim"></i>
            <h2>Virtual Tour</h2>
            <p>Let's make your home stand out with a high-quality virtual tour.</p>
          </div>
          <div class="service-item">
            <i class="fa-solid fa-image slideanim"></i>
            <h2>Photography</h2>
            <p>Beautiful, high-end photography is a central part of our marketing plan for your property.</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ElevatingRealEstate",
  };
  </script>
  
  <style scoped>
  .content-container {
    display: flex;
    flex-direction: column; /* Stack the sections vertically */
    justify-content: center;    /* Centers content horizontally */
    align-items: center;        /* Centers content vertically */
    min-height: 100vh;              /* Full viewport height */
    width: 100vw;                /* Full width */
    text-align: center;         /* Ensures text alignment in the container */
    padding: 50px;
  }
  
  h1 {
    font-size: 3rem; /* Large font size for the heading */
    font-weight: bold; /* Make the heading bold */
  }
  
  p {
    font-size: 1.3rem; /* Larger font size for paragraph text */
    line-height: 1.9; /* Improve readability with increased line height */
  }
  
  /* Services section */
  .services-section {
    margin-top: 50px;
    width: 100%; /* Make the services section take full width */
  }
  
  .services-row {
    display: flex;
    justify-content: space-between; /* Distribute service items evenly */
    align-items: stretch;
    gap: 20px;
    width: 100%;
    max-width: 1200px; /* Set a max-width to prevent stretching on large screens */
    margin: 0 auto; /* Center the row */
  }
  
  .service-item {
    flex: 1; /* Ensure each service takes equal width */
    text-align: center;
    padding: 20px;
    background-color: #585858;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1); /* Add some shadow for depth */
    transition: transform 0.3s ease;
  }
  
  .service-item:hover {
    transform: translateY(-10px); /* Slight lift on hover */
  }
  
  .service-item i {
    font-size: 2.5rem;
    margin-bottom: 10px;
  }
  
  .service-item h2 {
    font-size: 1.5rem;
    margin: 10px 0;
  }
  
  .service-item p {
    font-size: 1rem;
    line-height: 1.5;
  }
  </style>
  
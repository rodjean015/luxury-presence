<template>
    <div class="container-center">
      <h1>The Selling Process</h1>
  
      <!-- First row of numbers -->
      <div class="numbers-row">
        <div class="number-item" v-for="(number, index) in numbers.slice(0, 10)" :key="index">
          <h1 class="slideanim">{{ number }}</h1>
        </div>
      </div>
      <hr />
  
      <!-- Second row of numbers -->
      <div class="numbers-row">
        <div class="number-item" v-for="(number, index) in numbers.slice(10, 20)" :key="index">
          <h1 class="slideanim">{{ number }}</h1>
        </div>
      </div>
      <br />

    </div>
  </template>
  
  <script>
  export default {
    name: "SellingProcess",
    data() {
      return {
        numbers: Array(20).fill(0), // Initial array with 20 numbers
      };
    },
    mounted() {
      // Start randomizing the numbers every 2 seconds
      this.randomizeNumbers();
    },
    methods: {
      randomizeNumbers() {
        setInterval(() => {
          this.numbers = this.numbers.map(() => Math.floor(Math.random() * 10)); // Generate random numbers between 0-9
        }, 100); // Change every 2 seconds
      },
    },
  };
  </script>
  
  <style scoped>
  .container-center {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-image: url('src/assets/bg/stacked-peaks-haikei.svg');
    min-height: 100vh; /* Full viewport height */
    text-align: center;
    width: 100vw; /* Ensure the container takes up full width */
    background-size: cover; /* Ensure the background fills the container */
    background-repeat: no-repeat; /* Prevent repeating the background */
    background-position: center; /* Center the background image */
  }
  
  .numbers-row {
    display: flex;
    justify-content: space-between; /* Space items with full width */
    align-items: center;
    margin-bottom: 20px;
    width: 100%; /* Make the row take up the full width */
  }
  
  .number-item {
    flex: 1; /* Ensure each item takes up equal width */
    text-align: center;
  }
  
  h1 {
    font-size: 3.5rem;
    margin: 0;
  }
  
  hr {
    border-top: 1px solid #ddd;
    width: 100%; /* Ensure the hr takes the full width */
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
  
  /* Responsive Design for smaller screens */
  @media (max-width: 768px) {
    .numbers-row {
      flex-direction: column; /* Stack items vertically on smaller screens */
    }
  
    .number-item {
      margin-bottom: 20px; /* Add more space between numbers in vertical layout */
    }
  
    .number-item h1 {
      font-size: 2rem;
    }
  }
  </style>
  
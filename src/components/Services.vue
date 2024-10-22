<template>
  <div class="portfolio">
    <header>
      <h1>{{ name }}</h1>
      <p>{{ tagline }}</p>
    </header>
    
    <!-- Button at the bottom -->
    <div class="appointment-section">
      <button class="appointment-button">Book an Appointment</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Services",
      tagline: "Comprehensive Marketing Plan",
    };
  }
};
</script>

<style scoped>
.portfolio {
  padding: 20px;
  text-align: center;
  color: #000000;
  
  /* Full screen background */
  min-height: 100vh;           /* Full viewport height */
  min-width: 100vw;            /* Full viewport width */
  background-image: url('src/assets/bg/wave-haikei (1).svg');
  background-size: cover;      /* Ensures background covers the full area */
  background-position: center; /* Centers the background */
  background-repeat: no-repeat; /* Prevents repeating the background */
  margin: 0;                    /* Removes default margin */
  display: flex;               /* Flexbox to center content */
  flex-direction: column;      /* Stack content vertically */
  justify-content: center;     /* Centers content vertically */
  align-items: center;         /* Centers content horizontally */
  position: relative;          /* Ensures button can be placed at the bottom */
}

h1, p {
  opacity: 0; /* Initially hidden */
  transform: translateY(50px); /* Start position: 50px below */
  animation: fadeInUp 2s ease-out forwards; /* Animation for both h1 and p */
}

/* Animation for fade in and upward movement */
@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0); /* Move to normal position */
  }
}

h1 {
  font-size: 10em;
  font-weight: 300;
  text-shadow: 4px 4px 8px rgba(173, 173, 173, 0.5); /* Adds a shadow effect */
  animation-delay: 0.5s; /* Delay the animation of h1 */
}

p {
  font-size: 4em;
  text-shadow: 3px 3px 6px rgba(182, 182, 182, 0.5); /* Adds a shadow effect */
  animation-delay: 1s; /* Delay the animation of p */
}

/* Appointment Section and Button */
.appointment-section {
  position: absolute;
  bottom: 50px; /* Position button 50px from the bottom */
  width: 100%;  /* Make sure the button is centered horizontally */
  display: flex;
  justify-content: center;
}

.appointment-button {
  padding: 15px 30px;
  font-size: 1.5em;
  color: #ffffff;
  background-color: #8d6d02;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.appointment-button:hover {
  background-color: #796700; /* Darker color on hover */
}
</style>

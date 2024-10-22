<template>
  <div>
    <!-- Carousel Section -->
    <div class="carousel-container">
      <div class="carousel-slide">
        <!-- Slide content based on activeIndex -->
        <div class="carousel-item" v-for="(slide, index) in slides" :key="index" v-show="index === activeIndex">
          <h4>{{ slide.title }}</h4>
          <p>{{ slide.content }}</p>
        </div>
      </div>
    </div>

    <!-- Logo Slider Section -->
    <div class="logo-container">
      <div class="logo-slider">
        <!-- Repeating brand logos in the slider -->
        <div class="logo-item" v-for="(logo, index) in logos" :key="index">
          <img :src="logo.src" :alt="logo.alt" />
        </div>
        <!-- Duplicate the logos for smooth continuous animation -->
        <div class="logo-item" v-for="(logo, index) in logos" :key="'repeat-' + index">
          <img :src="logo.src" :alt="logo.alt" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: 0, // Track the active slide index
      slides: [
        {
          title: 'Local Exposure',
          content:
            'Through our partnership with Nextdoor, the private online social network now used in over 80% of U.S. neighborhoods and virtually all Bay Area neighborhoods, we make sure your home receives targeted local exposure. When you list your home with Hansen Partners it will automatically appear on Nextdoor in your neighborhood.',
        },
        {
          title: 'National Exposure',
          content:
            'We secure strategic positioning and enhancement on Realtor.com, Trulia, and Zillow, driving more consumers to your home and increasing exposure. We will receive every inquiry about your property directly.',
        },
        {
          title: 'International Exposure',
          content:
            'To expose your luxury listing to millions of potential homebuyers worldwide, we promote on prominent international real estate portals, including: Wall Street Journal, LuxuryPortfolio.com, LuxuryRealEstate.com, LeadingRE.com, UniqueHomes.com, China.apr.com, Caimeiju, Juwai, Country Life UK.',
        },
      ],
      logos: [
        { src: 'src/logo/logo1.png', alt: 'Brand 1' },
        { src: 'src/logo/logo2.png', alt: 'Brand 2' },
        { src: 'src/logo/logo3.png', alt: 'Brand 3' },
        { src: 'src/logo/logo4.png', alt: 'Brand 4' },
        { src: 'src/logo/logo5.png', alt: 'Brand 5' },
        { src: 'src/logo/logo6.png', alt: 'Brand 6' },
        { src: 'src/logo/logo7.png', alt: 'Brand 7' },
        { src: 'src/logo/logo8.png', alt: 'Brand 8' },
        { src: 'src/logo/logo9.png', alt: 'Brand 9' },
      ],
    };
  },
  mounted() {
    this.startAutoSlide(); // Start automatic slide change when component is mounted
  },
  methods: {
    startAutoSlide() {
      setInterval(() => {
        this.activeIndex = (this.activeIndex + 1) % this.slides.length; // Loop through slides
      }, 3000); // Change every 3 seconds
    },
  },
};
</script>

<style scoped>
/* Carousel Styles */
.carousel-container {
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
  position: relative;
  margin-bottom: 30px; /* Adjust margin for less space */
}

.carousel-slide {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 300px;
}

.carousel-item {
  text-align: center;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  padding: 0; /* Remove extra padding */
}

h4 {
  font-size: 2.5rem; /* Slightly smaller font to adjust space */
  margin-bottom: 8px; /* Adjust for less space */
}

p {
  font-size: 1.1rem;
  line-height: 1.6; /* Reduce line height */
}

/* Logo Slider Styles */
.logo-container {
  width: 100vw;
  overflow: hidden;
  padding: 0; /* Remove padding to eliminate extra space */
  margin: 0; /* Remove margin */
}

.logo-slider {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  animation: scroll 50s linear infinite; /* Adjust speed of animation */
}

.logo-item {
  flex-shrink: 0;
  padding: 0 20px; /* Reduce padding between logos to minimize space */
}

.logo-item img {
  height: 50px;
  width: auto;
}

/* Keyframes for scrolling animation */
@keyframes scroll {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(-100%);
  }
}
</style>

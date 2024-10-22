<template>
  <div id="app">
    <Navbar />
    <Services />
    <!-- Place ElevatingRealEstate below Services -->
    <ElevatingRealEstate />
    <RealEstateSuccess />
    <IntentionalLayout />
    <SellingProcess />
    <DecorGuidance />
    <WeMarket />
    <LeadingRealEstate />
    <WorkWithUs />
    <ContactUs />
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Services from './components/Services.vue';
import ElevatingRealEstate from './components/ElevatingRealEstate.vue';
import RealEstateSuccess from './components/RealEstateSuccess.vue';
import IntentionalLayout from './components/IntentionalLayout.vue';
import SellingProcess from './components/SellingProcess.vue';
import DecorGuidance from './components/DecorGuidance.vue';
import WeMarket from './components/WeMarket.vue';
import LeadingRealEstate from './components/LeadingRealEstate.vue';
import WorkWithUs from './components/WorkWithUs.vue';
import ContactUs from './components/ContactUs.vue'
import Footer from './components/Footer.vue'


export default {
  components: {
    Navbar,
    Services,
    ElevatingRealEstate,
    RealEstateSuccess,
    IntentionalLayout,
    SellingProcess,
    DecorGuidance,
    WeMarket,
    LeadingRealEstate,
    WorkWithUs,
    ContactUs,
    Footer
  },
};
</script>

<style>
:root {
  --background-dark: #181818; /* Dark background */
  --text-light: #f8f8f8; /* Light text */
  --text-muted: rgba(255, 255, 255, 0.7); /* Muted text for contrast */
  --primary-dark: #2c3e50; /* Darker primary color */
}

/* Dark theme for the entire app */
#app {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  background-color: var(--background-dark); /* Dark background */
  color: var(--text-light); /* Light text for dark theme */
  display: flex;
  flex-direction: column; /* Stack components vertically */
  justify-content: flex-start; /* Align content to the top */
  align-items: center;
  width: 100vw;
  min-height: 100vh;
  margin: 0;
  transition: background-color 0.5s ease, color 0.5s ease; /* Smooth transition for theme change */
}

/* You can further customize components here for the dark theme */
h1, h2, h3, h4, h5, h6 {
  color: var(--text-light);
}

p {
  color: var(--text-muted); /* Muted text color for paragraphs */
}

a {
  color: var(--text-light); /* Link color */
}

a:hover {
  color: var(--primary-dark); /* Hover effect for links */
}
</style>

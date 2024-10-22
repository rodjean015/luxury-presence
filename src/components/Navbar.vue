<template>
  <nav :class="['navbar', { 'scrolled': isScrolled, 'hidden': isHidden }]">
    <div class="container">
      <div class="navbar-brand" :class="{ 'scrolled-brand': isScrolled }">
        <a href="#" class="navbar-logo">Jhansens</a>
      </div>

      <!-- Toggle button for mobile view -->
      <button class="navbar-toggler" @click="toggleNavbar">
        <span class="navbar-toggler-icon">&#9776;</span>
      </button>

      <!-- Navigation Links -->
      <div :class="['navbar-menu', { 'is-active': isActive }]">
        <ul class="navbar-links" :class="{ 'scrolled-links': isScrolled }">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      isScrolled: false,
      isHidden: false, // State to track if navbar is hidden
      lastScrollTop: 0, // Variable to track last scroll position
    };
  },
  methods: {
    toggleNavbar() {
      this.isActive = !this.isActive;
    },
    handleScroll() {
      const currentScroll = window.scrollY;

      // Check if the page has scrolled down past a threshold (50px)
      this.isScrolled = currentScroll > 50;

      // Hide navbar when scrolling down, show when scrolling up
      if (currentScroll > this.lastScrollTop) {
        this.isHidden = true; // Hide the navbar
      } else {
        this.isHidden = false; // Show the navbar
      }

      // Update the last scroll position
      this.lastScrollTop = currentScroll;
    },
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
};
</script>

<style scoped>
/* Basic Styling for Navbar */
.navbar {
  background-color: transparent; /* Transparent background */
  padding: 15px;
  position: fixed;
  top: 0;
  width: 100vw; /* Make navbar take full width of viewport */
  z-index: 1000;
  transition: background-color 0.3s ease, color 0.3s ease, top 0.3s ease; /* Added transition for smooth hide/show */
  left: 0; /* Ensure it starts from the left edge of the viewport */
  margin: 0; /* Ensure no margin around the navbar */
}

.navbar.scrolled {
  background-color: rgba(0, 0, 0, 0.8); /* Darker background when scrolled */
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* Shadow effect */
}

.navbar.hidden {
  top: -100px; /* Moves navbar out of view when hidden */
}

.navbar-brand {
  float: left;
}

.navbar-brand a {
  color: rgba(255, 255, 255, 0.9); /* Light color for brand */
  text-decoration: none;
  font-size: 1.5em;
}

.navbar-toggler {
  background-color: transparent; /* Set background to transparent */
  border: none; /* Remove border */
  color: white;
  font-size: 1.5em;
  cursor: pointer;
  display: none; /* Hidden by default (for mobile view) */
  float: right; /* Align to the right */
  margin-right: 15px; /* Add some space to the right */
}

.navbar-toggler:focus {
  outline: none; /* Remove focus outline */
}

.navbar-menu {
  display: flex;
  justify-content: flex-end; /* Aligns the links to the right */
  align-items: center;
}

.navbar-links {
  list-style-type: none;
  display: flex;
}

.navbar-links li {
  margin: 0 15px;
}

.navbar-links li a {
  color: rgba(255, 255, 255, 0.8); /* Default light color for links */
  text-decoration: none;
  font-size: 1.2em;
}

.navbar-brand.scrolled-brand a,
.navbar-links.scrolled-links li a {
  color: white; /* Pure white font when scrolled */
}

/* Responsive Styles */
@media (max-width: 768px) {
  .navbar-toggler {
    display: inline-block;
    background-color: transparent; /* Ensure transparent background on mobile */
    margin-right: 15px; /* Add space to the right */
  }

  .navbar-menu {
    display: none;
    flex-direction: column;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.9);
  }

  .navbar-menu.is-active {
    display: flex;
  }

  .navbar-links {
    flex-direction: column;
    text-align: center;
  }

  .navbar-links li {
    margin: 10px 0;
  }
}
</style>

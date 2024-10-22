<template>
    <footer class="container-fluid text-center">
      <a href="#myPage" title="To Top">
        <span class="glyphicon glyphicon-chevron-up"></span>
      </a>
      <p>Website Designed & Developed by Rodjean Verzosa</p>
      <p>&copy; 2024 | <a href="#" class="privacy-policy-link">Privacy Policy</a></p>
    </footer>
  </template>
  
  <script>
  export default {
    name: "FooterComponent",
  };
  </script>
  
  <style scoped>
  .container-fluid {
    padding: 20px;
    background-color: black;
    width: 100vw;
  }
  
  .text-center {
    text-align: center;
  }
  
  a {
    color: white;
    text-decoration: none;
  }
  
  a:hover {
    text-decoration: underline;
  }
  
  .glyphicon-chevron-up {
    font-size: 24px;
  }
  
  .privacy-policy-link {
    color: white;
  }
  
  .privacy-policy-link:hover {
    text-decoration: underline;
  }
  </style>
  
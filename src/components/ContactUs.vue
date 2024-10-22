<template>
    <div class="container contact-section" id="contact">
      <div class="row align-items-center justify-content-center">
        <!-- Left Side: Contact Information -->
        <div class="col-md-6 text-left">
          <h1>CONTACT US:</h1>
          <p>
            <span class="glyphicon glyphicon-map-marker"></span>
            4733 Chabot Drive #100 Pleasanton, CA 94588
          </p>
          <p>
            <span class="glyphicon glyphicon-phone"></span>
            (925) 553-6707
          </p>
          <p>
            <span class="glyphicon glyphicon-envelope"></span>
            luxuryhomesinwc@icloud.com
          </p>
          <p>Julie Hansen-Orvis | CA DRE# 00934447</p>
        </div>
        <br>
  
        <!-- Right Side: Contact Form -->
        <div class="col-md-6">
          <h2>Newsletter</h2>
          <p>Subscribe to our Newsletter for latest news and updates. Stay tuned!</p>
          <br>
          <form @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">Name:</label>
              <input
                type="text"
                id="name"
                v-model="form.name"
                :class="{'is-invalid': errors.name}"
              />
              <div v-if="errors.name" class="error-message">
                {{ errors.name }}
              </div>
            </div>
  
            <div class="form-group">
              <label for="email">Email:</label>
              <input
                type="email"
                id="email"
                v-model="form.email"
                :class="{'is-invalid': errors.email}"
              />
              <div v-if="errors.email" class="error-message">
                {{ errors.email }}
              </div>
            </div>
  
            <div class="form-group">
              <label for="message">Message:</label>
              <textarea
                id="message"
                v-model="form.message"
                :class="{'is-invalid': errors.message}"
              ></textarea>
              <div v-if="errors.message" class="error-message">
                {{ errors.message }}
              </div>
            </div>
  
            <button type="submit">Send</button>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          name: "",
          email: "",
          message: ""
        },
        errors: {
          name: null,
          email: null,
          message: null
        }
      };
    },
    methods: {
      validateForm() {
        let isValid = true;
        this.errors = {
          name: null,
          email: null,
          message: null
        };
  
        // Name validation
        if (!this.form.name) {
          this.errors.name = "Name is required.";
          isValid = false;
        }
  
        // Email validation
        const emailPattern = /^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$/;
        if (!this.form.email) {
          this.errors.email = "Email is required.";
          isValid = false;
        } else if (!emailPattern.test(this.form.email)) {
          this.errors.email = "Please enter a valid email.";
          isValid = false;
        }
  
        // Message validation
        if (!this.form.message) {
          this.errors.message = "Message is required.";
          isValid = false;
        }
  
        return isValid;
      },
      submitForm() {
        if (this.validateForm()) {
          // Perform form submission, e.g., via API or any other handling
          alert("Form submitted successfully!");
  
          // Reset form
          this.form.name = "";
          this.form.email = "";
          this.form.message = "";
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .contact-section {
    margin-top: 40px;
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    background-image: url('src/assets/bg/wave-haikei (2).svg');
    background-repeat: no-repeat;
    background-position: bottom; /* Ensures the image is at the bottom */
    background-size: cover; /* Ensures the image covers the entire width */
  }
  
  .text-left p {
    margin-bottom: 10px;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    font-weight: bold;
    display: block;
    margin-bottom: 5px;
  }
  
  input,
  textarea {
    width: 100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  
  textarea {
    min-height: 100px;
    resize: vertical;
  }
  
  button {
    padding: 10px 15px;
    background-color: #8d6d02;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    width: 100%;
  }
  
  button:hover {
    background-color: #796700;
  }
  
  .is-invalid {
    border-color: red;
  }
  
  .error-message {
    color: red;
    font-size: 0.875em;
    margin-top: 5px;
  }
  </style>
  
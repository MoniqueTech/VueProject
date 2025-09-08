<template>
  <main>
    <div class="Container">
      <form id="contactForm" @submit.prevent="handleSubmit">
        <h1>CONTACT ME</h1>

        <div class="form-group">
          <label for="name">Name:</label>
          <input
            type="text"
            id="name"
            placeholder="Your Name"
            v-model.trim="form.name"
          />
          <small class="error" v-if="errors.name">{{ errors.name }}</small>
        </div>

        <div class="form-group">
          <label for="email">Email:</label>
          <input
            type="email"
            id="email"
            placeholder="you@example.com"
            v-model.trim="form.email"
          />
          <small class="error" v-if="errors.email">{{ errors.email }}</small>
        </div>

        <div class="form-group">
          <label for="message">Message:</label>
          <textarea
            id="message"
            placeholder="Your message"
            rows="4"
            v-model.trim="form.message"
          ></textarea>
          <small class="error" v-if="errors.message">{{ errors.message }}</small>
        </div>

        <button type="submit">Submit Message</button>
      </form>
    </div>

    <!-- Modal -->
    <div id="modal" class="modal" v-show="showModal" @click.self="closeModal">
      <div class="modal-content">
        <span id="closeModal" class="close" @click="closeModal">&times;</span>
        <h2>Form Submitted Successfully</h2>
        <p><strong>Name:</strong><span> {{ form.name }}</span></p>
        <p><strong>Email:</strong><span> {{ form.email }}</span></p>
        <p><strong>Message:</strong><span> {{ form.message }}</span></p>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'ContactPage',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      },
      errors: {
        name: '',
        email: '',
        message: ''
      },
      showModal: false
    }
  },
  methods: {
    validate() {
      // reset errors
      this.errors = { name: '', email: '', message: '' }
      let ok = true

      if (!this.form.name) {
        this.errors.name = 'Please enter your name.'
        ok = false
      }
      if (!this.form.email) {
        this.errors.email = 'Please enter your email.'
        ok = false
      } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.form.email)) {
        this.errors.email = 'Please enter a valid email address.'
        ok = false
      }
      if (!this.form.message) {
        this.errors.message = 'Please enter a message.'
        ok = false
      }

      return ok
    },
    handleSubmit() {
      if (!this.validate()) return
      this.showModal = true
    },
    closeModal() {
      this.showModal = false
      // Optional: clear form after closing
      // this.form = { name: '', email: '', message: '' }
    }
  }
}
</script>

<style scoped>
* {
  margin: 0;
  border: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Karla', sans-serif;
  font-size: 14px;
}

h1 {
  padding: 20px;
  border-radius: 10px;
  text-align: center;
  background-color: #C2B8A3;
  color: #F5EFE6;
  font-size: 22px;
  font-weight: bold;
  font-family: 'Playfair Display', serif;
  margin-bottom: 20px;
  max-width: 400px;
  margin-left: auto;
  margin-right: auto;
}

form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  background-color: #F5EFE6;
  padding: 20px;
  border-radius: 10px;
  max-width: 400px;
  margin: auto;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

form label {
  font-weight: bold;
  color: #6B4C3B;
  font-size: 15px;
}

form input,
form textarea {
  padding: 10px;
  font-size: 15px;
  border-radius: 10px;
  border: 1px solid #ccc;
  background-color: #fff;
  color: #6B4C3B;
  resize: vertical;
}

form button {
  padding: 12px;
  font-size: 16px;
  background-color: #A2583F;
  color: #F5EFE6;
  font-weight: bold;
  border-radius: 5px;
  cursor: pointer;
  border: none;
  transition: background-color 0.3s ease;
}

form button:hover {
  background-color: #A12D21;
}

small.error {
  color: red;
  font-size: 15px;
  font-weight: bold;
  margin-top: 2px;
  display: block;
}

/* Modal */
.modal {
  display: block; /* controlled by v-show */
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}

.modal-content {
  background-color: #F5EFE6;
  margin: 10% auto;
  padding: 20px;
  border-radius: 10px;
  max-width: 500px;
  text-align: center;
  color: #6B4C3B;
  position: relative;
}

.modal-content h2 {
  margin-bottom: 15px;
  font-size: 16px;
}

.modal-content p {
  margin: 10px 0;
  font-size: 15px;
}

.modal-content span {
  margin-left: 5px;
  font-weight: normal;
}

.close {
  color: #A2583F;
  position: absolute;
  right: 16px;
  top: 8px;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
}

.close:hover {
  color: #A12D21;
}

@media (min-width: 768px) {
  main { padding: 40px; }
  h1 { font-size: 36px; }
}
</style>

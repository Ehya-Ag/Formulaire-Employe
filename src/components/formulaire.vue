<template>
  <div class="employee-form">
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="name">Nom :</label>
        <input type="text" id="name" required v-model="name">
      </div>
      <div class="form-group">
        <label for="email">Email :</label>
        <input type="email" id="email" required v-model="email">
      </div>
      <div class="form-group">
        <label for="numero">Numéro de téléphone :</label>
        <input type="tel" id="numero" required v-model="numero">
      </div>
      <button type="submit">Envoyer</button>
    </form>

    <div v-if="submitted">
      <h3>Informations soumises :</h3>
      <p><strong>Nom :</strong> {{ name }}</p>
      <p><strong>Email :</strong> {{ email }}</p>
      <p><strong>Numéro de téléphone :</strong> {{ numero }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'Ehya',
      email: '',
      numero: '',
      submitted: false
    };
  },
  methods: {
    submitForm() {
      this.submitted = true;
    }
  }
};
</script>

<style scoped>
.employee-form {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
  border-radius: 5px;
}

form {
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 10px;
}

label {
  font-weight: bold;
}

input {
  display: block;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 3px;
}

button {
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

h3 {
  margin-top: 20px;
  font-size: 1.2em;
}

p {
  margin: 5px 0;
}

strong {
  font-weight: bold;
}
</style>

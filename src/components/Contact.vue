<template>
  <div>
    Contact Page
    <h1>We are located in Varna</h1>
    <div>
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d186126.44345323008!2d27.80282489072861!3d43.204755644600745!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x40a4538baaf3d7a1%3A0x5727941c71a58b7c!2z0JLQsNGA0L3QsA!5e0!3m2!1sbg!2sbg!4v1646636122398!5m2!1sbg!2sbg"
        width="600"
        height="450"
        style="border: 0"
        allowfullscreen=""
        loading="lazy"
      ></iframe>
    </div>
    <div v-if="!isHidden">
      <div>
        <label for="name">Име: </label>
        <input type="text" placeholder="Име" id="name" v-model="name" />
      </div>
      <div>
        <label for="email">Имейл: </label>
        <input type="email" placeholder="Имейл" id="email" v-model="email" />
      </div>
      <div>
        <label for="phone">Телефон: </label>
        <input type="number" placeholder="Телефон" id="phone" v-model="phone" />
      </div>
      <div>
        <label for="message">Съобщение: </label>
        <textarea
          id="message"
          cols="30"
          rows="4"
          placeholder="Съобщение"
          v-model="message"
        ></textarea>
      </div>
      <button
        v-on:click="isHidden = true"
        style="font-size: 25px; margin-top: 20px"
      >
        Изпрати
      </button>
    </div>
    <div v-if="isHidden" id="text-container">
      <div v-html="doSomething()"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      name: "",
      email: "",
      phone: "",
      message: "",
      html: "",
      isHidden: false,
    };
  },
  methods: {
    doSomething() {
      this.html = "Name:" + this.name + "<br>" + "Email: " + this.email;
      return this.html;
    },
  },
};
</script>

<style scoped>
div {
  margin-top: 20px;
  font-size: 25px;
  color: white;
}
</style>

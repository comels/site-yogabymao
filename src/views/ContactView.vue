<script setup>
import { ref } from "vue";
import Email from "../assets/stmp/smtp";

const name = ref("");
const email = ref("");
const phone = ref("");
const message = ref("");
const merci = ref(false);

const emailSend = () => {
  Email.send({
    SecureToken: "a4e5869b-bf62-4d37-9072-cdc66a88fefa",
    To: "comelesauter@gmail.com",
    From: "come.l.s@hotmail.fr",
    Subject: "Yoga Contact",
    Body:
      "<b>Nom : </b>" +
      name.value +
      "<br/><br/><b>Email : </b>" +
      email.value +
      "<br/><br/><b>Portable : </b>" +
      phone.value +
      "<br/><br/><b>Message : </b>" +
      message.value,
  }).then(() => (merci.value = true));
  name.value = "";
  email.value = "";
  phone.value = "";
  message.value = "";
};
</script>

<template>
  <section class="bg-white">
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
      <h2 class="mb-4 text-3xl font-medium text-center text-gray-900">
        ME CONTACTER
      </h2>
      <p class="mb-8 lg:mb-16 font-light text-center text-white0 sm:text-lg">
        Got a technical issue? Want to send feedback about a beta feature? Need
        details about our Business plan? Let us know.
      </p>
      <p v-if="merci" class="mb-5 text-sm text-center text-kaki">
        Votre message à bien été envoyé.
      </p>
      <form @submit.prevent="emailSend" class="space-y-8" name="contactyoga">
        <div>
          <input
            v-model="name"
            type="text"
            id="name"
            name="name"
            class="block p-3 w-full text-gray-800 border focus:border-transparent focus:ring-black bg-white text-sm"
            placeholder="NOM PRÉNOM"
            required
          />
        </div>
        <div>
          <input
            v-model="email"
            type="email"
            name="email"
            class="text-gray-800 border focus:border-transparent focus:ring-black text-sm block w-full p-2.5"
            placeholder="EMAIL"
            required
          />
        </div>
        <div>
          <input
            v-model="phone"
            type="tel"
            name="phone"
            class="bg-white text-gray-800 border focus:border-transparent focus:ring-black text-sm block w-full p-2.5"
            placeholder="TÉLÉPHONE ( FACULTATIF )"
          />
        </div>
        <div class="sm:col-span-2">
          <textarea
            v-model="message"
            name="message"
            rows="6"
            class="block p-2.5 w-full text-sm border focus:border-transparent focus:ring-black text-gray-800 bg-white"
            placeholder="VOTRE MESSAGE"
            required
          ></textarea>
        </div>
        <button
          type="submit"
          class="py-3 px-10 text-sm font-medium text-center text-white bg-kaki sm:w-fit focus:outline-none"
        >
          ENVOYER
        </button>
      </form>
    </div>
  </section>
</template>

<style lang="scss" scoped>
* {
  font-family: "Montserrat", sans-serif;
}
</style>

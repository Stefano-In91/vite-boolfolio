<script>
export default {
  name: "AppHeader",
};
</script>

<template>
  <header>
    <ul>
      <li><router-link :to="{ name: 'homepage' }">Home Page</router-link></li>
      <li><router-link :to="{ name: 'about-us' }">Chi Siamo</router-link></li>
      <li><router-link :to="{ name: 'contact-us' }">Contatti</router-link></li>
    </ul>
  </header>
</template>

<style></style>

<script>
import axios from "axios";
import AppCard from "./AppCard.vue";

export default {
  name: "AppMain",
  components: {
    AppCard,
  },

  data() {
    return {
      api_url: "http://127.0.0.1:8000/api/projects",
      projects: [],
    };
  },

  created() {
    axios.get(this.api_url).then((res) => {
      this.projects = res.data;
    });
  },
};
</script>

<template>
  <main>
    <div v-for="project in projects">
      <AppCard :data="project" />
    </div>
  </main>
</template>

<style></style>

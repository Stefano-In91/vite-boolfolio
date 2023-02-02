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
    <div class="row">
      <div class="col" v-for="project in projects">
        <AppCard :data="project" />
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped></style>

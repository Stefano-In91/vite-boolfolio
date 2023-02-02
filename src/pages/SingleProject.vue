<script>
import axios from "axios";
import AppCard from "../components/AppCard.vue";

export default {
  name: "SingleProject",
  components: {
    AppCard,
  },
  data() {
    return {
      api_url: "http://127.0.0.1:8000/api/projects",
      project: null,
    };
  },
  created() {
    axios
      .get(this.api_url + "/" + this.$route.params.slug)
      .then((res) => {
        this.project = res.data;
      })
      .catch((err) => {
        console.log(err);
        this.$router.push({ name: "page-404" });
      });
  },
};
</script>

<template>
  <AppCard :data="project" />
</template>

<style lang="scss" scoped></style>

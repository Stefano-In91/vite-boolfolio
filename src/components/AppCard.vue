<script>
export default {
  name: "AppCard",
  props: {
    data: Object,
  },
  methods: {
    truncate(string) {
      return string.substring(0, 250) + "...";
    },
  },
};
</script>

<template>
  <div class="card">
    <img v-if="data.cover_image" :src="data.cover_image" class="card-img-top" :alt="data.title" />
    <div class="card-body">
      <h5 class="card-title">{{ data.title }}</h5>
      <p class="card-text">
        {{ truncate(data.description) }}
      </p>
      <span v-if="data.type">{{ data.type.name }}</span>
      <span v-for="technology in data.technologies" class="badge bg-secondary"
        >{{ technology.name }}
      </span>
    </div>
  </div>
</template>

<style></style>

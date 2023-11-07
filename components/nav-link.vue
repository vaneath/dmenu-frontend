<template>
  <li v-if="type == 'text'">
    <nuxt-link id="nav-link-text" :class="mergedClass" :to="props.to">{{
      props.title
    }}</nuxt-link>
  </li>
  <li
    v-if="type == 'button'"
    class="px-7 py-1.5 bg-secondary hover:bg-opacity-90 rounded-md"
  >
    <nuxt-link id="nav-link-button" :class="mergedClass" :to="props.to">{{
      props.title
    }}</nuxt-link>
  </li>
</template>

<script setup>
const props = defineProps({
  class: {
    type: String,
  },
  to: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  type: {
    type: String,
    default: "text",
  },
});

const mergedClass = computed(() => {
  switch (props.type) {
    case "button":
      return `text-sm text-white font-medium ${props.class}`;
    default:
      return props.class;
  }
});
</script>

<style scoped>
#nav-link-text {
  display: inline-block;
  padding-bottom: 2px;
  background-image: linear-gradient(#f8b300 0 0);
  background-position: 0 100%;
  background-size: 0% 2px;
  background-repeat: no-repeat;
  transition:
    background-size 0.3s,
    background-position 0s 0.3s;
}

#nav-link-text:hover {
  background-position: 100% 100%;
  background-size: 100% 2px;
}
</style>

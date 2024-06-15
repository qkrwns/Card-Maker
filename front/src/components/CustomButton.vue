<template>
  <div>
    <v-btn>{{ text }}</v-btn>
  </div>
</template>

<script>
export default {
  props: {
    text: String,
  },
};
</script>

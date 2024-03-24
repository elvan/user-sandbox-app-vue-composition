<template>
  <section class="container">
    <h2>{{ userName }}</h2>
  </section>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const uName = ref('Elvan');

    setTimeout(function() {
      uName.value = 'Hidayat';
    }, 2000);

    return { userName: uName };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  max-width: 30rem;
  margin: 3rem auto;
  padding: 1rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
</style>

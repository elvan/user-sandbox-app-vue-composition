<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ age }}</h3>
    <button @click="setAge">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" v-model="firstName" />
      <input type="text" placeholder="Last Name" v-model="lastName" />
    </div>
  </section>
</template>

<script>
import { computed, ref } from 'vue';

export default {
  setup() {
    const firstName = ref('');
    const lastName = ref('');
    const uAge = ref(31);

    const uName = computed(function () {
      return firstName.value + ' ' + lastName.value;
    });

    function setNewAge() {
      uAge.value = 33;
    }

    return {
      userName: uName,
      age: uAge,
      setAge: setNewAge,
      firstName,
      lastName,
    };
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

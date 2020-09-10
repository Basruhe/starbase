<template>
  <div id="app">
    <h3>{{title}}</h3>
    <button class="btn btn-primary" @click="fetchCharacter">Test Fetch Character</button>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team",
    };
  },
  methods: {
    fetchCharacter() {
      fetch("http://swapi.co/api/people", {
        method: "get",
      }).then((response) => console.log(response));
    },
  },
};
</script>

// Note: CORS error in console log. run in chrome without web security?
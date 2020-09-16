<template>
  <div class>{{character}}</div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      character: {},
    };
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.dev/api/people/${id}`, {
        method: "GET",
      })
        .then((response) => response.json())
        .then((json) => (this.character = json));
    },
  },
  created() {
    this.fetchCharacter(this.id);
  },
};
</script>
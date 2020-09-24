<template>
  <div class="col-md-4">
    <div class="character-card">
      <div class="card-block center-items" @click="switchCharacter">
        <h4 class="card-title">{{ character.name }}</h4>
        <p class="card-text">Height: {{ character.height }} cm</p>
        <p class="card-text">Mass: {{ character.mass }} kg</p>
        <p class="card-text">Hair Color: {{ character.hair_color }}</p>
        <p class="card-text">Eye Color: {{ character.hair_color }}</p>
      </div>
      <button type="button" class="btn btn-dark more-info">More info</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      character: {}
    };
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.dev/api/people/${id}`, {
        method: "GET"
      })
        .then(response => response.json())
        .then(json => (this.character = json));
    },
    switchCharacter() {
      let random_id = Math.floor(Math.random() * 83) + 1;
      this.fetchCharacter(random_id);
    }
  },
  created() {
    this.fetchCharacter(this.id);
  }
};
</script>

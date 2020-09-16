<template>
  <div id="app">
    <h3>{{title}}</h3>
    <div class="col-md-12">
      <Character v-for="(id, index) in initial_ids" :id="id" key="index" />
    </div>

    <!-- <button class="btn btn-primary" @click="fetchCharacter">Test Fetch Character</button> -->
  </div>
</template>



<script>
import Character from "./components/Character.vue";

export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team",
      initial_ids: [1, 13, 14],
    };
  },
  components: {
    Character,
  },
};
</script>

// Note: CORS error in console log. 
// Solution: run on firefox, with 'cors everywhere' extenstion active
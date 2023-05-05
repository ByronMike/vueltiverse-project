<template>
  <search-input class="-mt-12" />

  <div class="flex flex-wrap">
    <template
      v-for="({ image, name, species, status }, index) in data"
      :key="'character-card-' + index"
    >
      <character-card
        :image="image"
        :title="name"
        :subtitle="species"
        :status="status"
      />
    </template>
    <statistics :alive-count="aliveCount" />
  </div>
</template>

<script setup>
import { useStore } from "vuex";
import { computed, onMounted } from "vue";

// COMPONENTS
import SearchInput from "../components/SearchInput.vue";
import CharacterCard from "../components/CharacterCard.vue";
import Statistics from "../components/Statistics.vue";

const store = useStore();

onMounted(() => {
  store.dispatch('getCharacters');
});

const data = computed(() => {
  return store.state.charactersModule.data;
});

const aliveCount = computed(() => {
  return data.value.filter((character) => character.status === "Alive").length;
});

</script>

<script>
import { store } from '../store';

export default {

    name: 'AppSelect',

    data() {
        return {
            store,
        }
    }
  }

</script>

<template>

  <div class="select-wrapper">
    <div class="container">
      <select v-model="store.selectedArchetypeIndex" name="card-select" id="card-select" @change="$emit('search')">

        <option disabled value="">Choose Archetype</option>

        <option value="-1">All</option>

        <option 
          v-for="(currentArchetype, index) in store.archetypes" 
          :value="index"
        >
          {{ currentArchetype.archetype_name }}
        </option>

      </select>
    </div>
  </div>

</template>

<style lang="scss">

@use '../styles/variables' as *; 

.select-wrapper {
  background-color: $primary;
  padding: 0px 10px;

  .container {
    max-width: 1680px;
    margin: auto;
    padding: 25px 10px;

    select {
      padding: 10px;
      background-color: white;
      color: black;
      border-radius: 10px;
      box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.5);
    }
  }
}

</style>
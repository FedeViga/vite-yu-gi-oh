<script>
import axios from 'axios';
import AppNav from './components/AppNav.vue';
import AppSelect from './components/AppSelect.vue';
import AppMain from './components/AppMain.vue';

import {store} from './store.js'

export default {

  data() {
    return {
      cards: [],
      store
    }
  },

  created() {

    // chiamata axios per ottenere le prime 20 cards dall'api
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(result => {
      this.store.cards = result.data.data;
      this.store.loaded = true;
    })

    // chiamata axios per ottenere tutti gli archetypes delle cards 
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(result => {
      this.store.archetypes = result.data;
    })
  },

  methods: {

    // metodo per filtrare le cards in base all'archetype selezionato
    searchCards() {

      // caricamento
      this.store.loaded = false;

      // variabile dove salvo l'archetype selezionato
      let selectedArchetype = (this.store.archetypes[this.store.selectedArchetypeIndex].archetype_name);
      console.log(selectedArchetype);

      // chiamata axios
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=' + selectedArchetype).then(result => {
      console.log(result.data.data)
      this.store.cards = result.data.data;

      // caricamento
      this.store.loaded = true;
    })
    }
  },

  components: {
    AppNav,
    AppSelect,
    AppMain,
  },
}
</script>

<template>

  <AppNav></AppNav>

  <AppSelect @search="searchCards()"></AppSelect>

  <AppMain></AppMain>

</template>

<style lang="scss">

@use './styles/general' as *;

</style>
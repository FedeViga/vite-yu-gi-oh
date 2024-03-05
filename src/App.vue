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

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(result => {
      console.log(result.data.data)
      this.store.cards = result.data.data;
      this.store.loaded = true;
    })

    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(result => {
      this.store.archetypes = result.data;
      console.log(this.store.archetypes);
    })
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

  <AppSelect></AppSelect>

  <AppMain></AppMain>

</template>

<style lang="scss">

@use './styles/general' as *;

</style>
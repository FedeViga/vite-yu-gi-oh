<script>
import axios from 'axios';
import AppNav from './components/AppNav.vue';
import AppMain from './components/AppMain.vue';

export default {

  data() {
    return {
      cards: [],
    }
  },

  created() {

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(result => {
      console.log(result.data.data)
      this.cards = result.data.data;
    })
  },

  components: {
    AppNav,
    AppMain,
  },
}
</script>

<template>

  <AppNav></AppNav>

  <AppMain></AppMain>

</template>

<style lang="scss">

@use './styles/general' as *;

</style>
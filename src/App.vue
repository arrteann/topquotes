<template>
  <div id="app">
    <!-- HEADER -->
    <app-header :quoteLength="quotes.length" :maxLength="maxQuote"></app-header>
    <!-- QUOTES -->
    <app-quotes :quotes="quotes" @quoteDelete="deleteQoute"></app-quotes>
  </div>
</template>

<script>
import HeaderVue from "./components/Header.vue";
import QouteGridVue from './components/QouteGrid.vue';
export default {
  name: "App",
  data() {
    return {
      quotes: [],
      maxQuote: 10,
    };
  },
  components: {
    "app-header": HeaderVue,
    "app-quotes":QouteGridVue,
  },
  methods:{
    deleteQoute(index){
      this.quotes.splice(index,1);
    }
  }
};
</script>

<style lang="scss">
@import "./styles/_varibales.scss";
#app {
  padding: 1rem 1.5rem;
}
body {
  background-color: $back;
  height: 100vh;
}
</style>

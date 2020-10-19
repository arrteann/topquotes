<template>
  <main>
    <!-- ADD QUOTE -->
    <child-add-quote @quoteAdded="newQuote"></child-add-quote>
    <!-- SHOW QUOTES -->
    <div class="grid">
      <child-quote v-for="(quote,index) in quotes" :key="index" @click.native="deleteQuote(index)">
        <p>
          {{ quote }}
        </p>
      </child-quote>
    </div>
  </main>
</template>

<script>
import AddQuotesVue from "./AddQuotes.vue";
import Quote from "./Quote";
export default {
  props: ["quotes"],
  components: {
    childQuote: Quote,
    childAddQuote: AddQuotesVue,
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= 10) {
        alert("More than 10");
      } else {
        if (quote == "") {
          alert("Please Fill Box");
        } else {
          this.quotes.push(quote);
        }
      }
    },
    deleteQuote(index){
      this.$emit('quoteDelete',index)
    }
  },
};
</script>


<style lang="scss" scoped>
.grid {
  width: 100%;
  margin: 0 auto;
}
</style>
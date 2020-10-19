<template>
  <div>
    <label for="quote">add quote</label>
    <input
      type="text"
      id="quote"
      placeholder="new quote"
      required
      v-model="quote"
    />
    <br />
    <button @click.prevent="addQuote">add quote</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: "",
    };
  },
  methods :{
    addQuote(){
      this.$emit('quoteAdded',this.quote);
      this.quote = '';
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../styles/_varibales.scss";
div {
  background: #ee4540;
  padding: 1.5rem 1rem;
  border-radius: 4px;
  margin: {
    top: 40px;
    bottom: 20px;
  }
  label {
    text-transform: uppercase;
    color: $text;
    display: block;
    margin : {
      bottom: 10px;
    }
  }
  input {
    width: 90%;
    border: none;
    border-radius: 4px;
    padding: 8px 16px;

    &:placeholder-shown {
      text-transform: uppercase;
    }
  }
  button {
    cursor: pointer;

    margin: {
      top: 10px;
    }
    padding: 8px 16px;
    border: none;
    border-radius: 3px;
    text-transform: uppercase;
    border: 1px solid $text;
    background: transparent;
    color: $text;

    transition: all 0.6s ease-in;

    &:active{
      box-shadow: 0 2px 6px rgba($color: #000000, $alpha: 0.2);
      outline: none;
    }

    &:hover {
      background: $text;
      color: $back;
    }
  }
}
</style>
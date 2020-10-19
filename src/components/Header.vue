<template>
  <header>
    <h1>Best Quotes</h1>
    <div class="progress-container">
      <div class="progress-back"></div>
      <div
        class="progress"
        :style="{ width: (quoteLength / maxLength) * 100 + '%' }"
      >
        <span> {{ maxLength - quoteLength }} </span>
      </div>
    </div>
  </header>
</template>


<script>
export default {
  props: {
    quoteLength: Number,
    maxLength: Number,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/_varibales.scss";
h1 {
  margin : {
    top: 20px;
  }
  color: $text;
  text-align: center;
  text-transform: uppercase;
  font-weight: 200;
  letter-spacing: 4px;
}
.progress-container {
  width: 96%;
  height: 30px;
  margin: 0 auto;
  position: relative;
  .progress-back,
  .progress {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 100%;
    border-radius: 4px;
  }

  .progress-back {
    background: #f0f0f0;
    z-index: 0;
  }

  .progress {
    z-index: 1;
    transition: width 0.6s ease-in;
    background-color: blueviolet;
    width: 0%;
    display: flex;
    align-items: center;
    span {
      display: inline-block;
      margin-left: 15px;
      color: $text;
    }
  }
}
</style>
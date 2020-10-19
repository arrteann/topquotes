<template>
  <div class="up">
    <slot>

    </slot>
    
  </div>
</template>

<script>
export default {

};
</script>

<style lang="scss" scoped>
@import "../styles/_varibales.scss";
div {
  background: $text;
  padding: 20px 30px;
  border-radius: 3px;
  cursor: pointer;

  transition: all .5s ease;
  margin: 20px 0px;
}
.up{
  animation: up 1s ease forwards;
}
p{
  text-transform: uppercase;
}
@keyframes up{
  from{
    opacity: 0;
  }
  to{
    opacity: 1;
  }
}
</style>
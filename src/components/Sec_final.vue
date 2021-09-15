<template>
    <section>
        <div class="title"></div>
        <div class="traco"></div>
        <button></button>
    </section>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
section {
    background-image: url('../assets/background4.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    height: 430px;
    width: 100%;
}
</style>

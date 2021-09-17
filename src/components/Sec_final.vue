<template>
    <section class="secao-final">
        <div class="title">JUNTE-SE <br /> À BATALHA</div>
        <div class="divisor"></div>
        <!-- <div ></div> -->
        <button class="jogue-agora">JOGUE GRATUITAMENTE AGORA</button>
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
@import '../_global.scss';

.secao-final{
    background-image: url('../assets/background4.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: top;
    height: 430px;
    width: 100%;

    font-size: 70px;
    text-align: left;

    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 20px;

    padding: 50px 150px;

    .divisor{
        @include divisor;
    }
    .jogue-agora {
        @include botao;
        text-align: center;
        padding: 10px;
        font-size: 20pt;
        width: 100%;
    }
}
</style>

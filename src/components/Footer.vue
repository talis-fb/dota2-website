<template>
    <footer>
        <div class="marcas">
            <img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/valve_logo.png" height="30"  alt="">
            <img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/footer_logo.png" height="30" alt="">
        </div>
        <div class="legenda">Dota e o logotipo do Dota são marcas e/ou marcas registradas da Valve Corporation. 2021 Valve Corporation, todos os direitos reservados.</div>
    </footer>
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
footer {
    background-color: black;
    padding: 30px 100px;
    & > div {
        max-width: 500px;
        margin: 0 auto;
    }
    .marcas{
        display: flex;
        justify-content: space-between;
        padding: 30px;
    }
}
</style>

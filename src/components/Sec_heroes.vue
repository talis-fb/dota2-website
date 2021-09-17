<template>
    <section class="herois">
        <div class="main-title">
            <h1>QUEM VOCÊ </h1>
            <h2>ESCOLHERÁ?</h2>
        </div>
        <div class="divisor"></div>
        <div class="sub-title">
            <h3>De engenhosos magos a brutamontes destemidos, passando por rebeldes astutos, a gama de heróis do Dota 2 é enorme e incrivelmente diversa. Lance habilidades incríveis e Ultimates devastadoras no seu caminho para a vitória.</h3>
            <a href="/"> VER TODOS OS HERÓIS </a>
        </div>
        <GridHeroes />
    </section>
</template>

<script>
import GridHeroes from './Sec_grid_heroes.vue'


// <------------------- ADICIONA ISSO NO CLICO DE VIDA DO COMPONENTE
window.addEventListener("load", () => {
    let titulo_animado = document.querySelector('.main-title')
    const callback = (e) => { 
        if( e[0].isIntersecting ){
            // Aqui seta as propriedades dele visivel
        }else{
            // Aqui seta ele apagado
        }
    }
    // Observador
    let observer = new IntersectionObserver(callback, { threshold: [1] });
    observer.observe(titulo_animado);
}, false);
// --------------------------------


export default {
    name: 'App',
    components: {
        GridHeroes
    }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Laila:wght@500&display=swap');
@import '../global';

.herois {
    //Image
    background-image: url("https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/home/heroes_full.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;

    img {
        width: 100%;
        max-width: 1600px;
    }

    .main-title {
        margin-top: 900px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        h1{
            font-size: 70px;
        }
        h2 {
            font-size: 100px;
        }
    }

    .sub-title {
        max-width: 1000px;
        text-align: center;
        a{
            margin: 0 auto;
            width: 500px;
            @include botao;
            text-align: center;
            padding: 10px;
            font-size: 20pt;
        }
    }
}
</style>

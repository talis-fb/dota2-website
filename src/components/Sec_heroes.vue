<template>
    <section class="herois">
        <div class="shadow-layer"></div>
        <div class="main-title" :style="style_title" >
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

export default {
    name: 'App',
    components: {
        GridHeroes
    },
    data: function(){
        return {
            state_visibility_title: false
        }
    },
    computed: {
        style_title: function(){
            return this.state_visibility_title ? { opacity: 1, transform: 'translateY(-50px)' } : { opacity: 0, transform: 'translateY(0px)' }
        }
    },
    mounted: function(){
        let titulo_animado = document.querySelector('.main-title')
        const callback = (e) => this.state_visibility_title = !!e[0].isIntersecting // Retorna um booleano, que esta relacionado se o está na tela atual
        let observer = new IntersectionObserver(callback, { threshold: [0.5] }) // Observador
        observer.observe(titulo_animado);
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

    overflow: hidden;

    .shadow-layer{
        pointer-events: none;
        position: absolute;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0) linear-gradient(to top, rgba(0, 0, 0, 0) 60%, rgba(0, 0, 0, 0.733) 90%, rgb(0, 0, 0) 100%) repeat scroll 0% 0%;
    }

    img {
        width: 100%;
        max-width: 1600px;
    }

    .main-title {
        transition: ease 1s;
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

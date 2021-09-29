<template>
    <section class="grid-herois">
        <div class="shadow-layer-left"></div>
        <div class="shadow-layer-right"></div>
        <div class="grid-line grid-1" :style="{ width: width_row() }">
            <Hero 
             v-for="(i) of third_heroes(1)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i.name" 
             />
        </div>
        <div class="grid-line grid-2" :style="{ width: width_row() }">
            <Hero 
             v-for="(i) of third_heroes(2)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i.name" 
             />
        </div>
        <div class="grid-line grid-3" :style="{ width: width_row() }">
            <Hero 
             v-for="(i) of third_heroes(3)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i.name" 
             />
        </div>
    </section>
</template>

<script>
import Hero from './Hero.vue'
import heroes_source from './heroes.json'

export default {
    name: 'App',
    components: {
        Hero
    },
    data: function(){
        return{
            heroes_source
        }
    },
    methods:{
        third_heroes: function(part){
            const size = heroes_source.length
            const by = ( (size/3) * (part-1) )
            const until = ( (size/3) * part )
            // Ta faltando o zé 0
            const array = heroes_source.filter( (e, index) => ( by < index && index < until) )
            return [ ...array, ...array ]
        },
        width_row: function(){
            const with_hero = 225
            const quant_heroes_row = this.third_heroes / 3
            return `${quant_heroes_row * with_hero}px`
        }
    }
}
</script>

<style lang="scss" scoped>
.grid-herois {
    height: 800px;
    overflow: hidden;
    background-position: repeat-x;

    // mask-image: linear-gradient(to right, transparent 0%, black 20%, black 80%, transparent 100%);

    .shadow-layer-right {
        position: absolute;

        background: linear-gradient(to left, #000000 0%, #000000 5%, #ffffff00 100%);

        ///background-color: red;
        width: 1%;
        height: 100%;
        bottom: 0;
        right: 0;
        z-index: 9;
        pointer-events: none;
    }

    .shadow-layer-left {
        position: absolute;
        background: linear-gradient(to right, #000000 0%, #000000 5%, #ffffff00 100%);
        width: 1%;
        height: 100%;
        bottom: 0;
        left: 0;
        z-index: 9;
        pointer-events: none;
    }

    // ---
    margin: 0 auto;
    position: relative;
    overflow: hidden;
    transform: translate3d(0, 0, 0);
    // --

    & > div {
        display: flex;
        justify-content: left;
        align-items: center;
        gap: 10px;
        height: 175px; // Definir a altura proxima ao dos blocos dos herois obriga ele à ficar em uma unica linha, com overflow fora da tela
    }
    .grid-line {
        animation: moveSlideshow 48s linear infinite; 
    }
    .grid-1{
        animation-direction: normal;
    }
    .grid-2{
        animation-direction: reverse;
    }
    .grid-3{
        animation-direction: normal;
    }
}

@keyframes moveSlideshow {
    0% {
        transform: translateX(0%);
    }

    100% { 
        transform: translateX(-50%);  
    }
}

</style>

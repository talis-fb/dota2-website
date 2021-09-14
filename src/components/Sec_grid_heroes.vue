<template>
    <section class="grid-herois">
        <div class="grid-line grid-1" :style="{ width: width_row() }">
            <Hero 
             v-for="(i) of third_heroes(1)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i" 
             />
        </div>
        <div class="grid-line grid-2" :style="{ width: width_row() }">
            <Hero 
             v-for="(i) of third_heroes(2)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i" 
             />
        </div>
        <div class="grid-line grid-3" :style="{ width: width_row() }">
            <Hero 
             v-for="(i) of third_heroes(3)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i" 
             />
        </div>
    </section>
</template>

<script>
//import func from 'vue-editor-bridge'
    import Hero from './Hero.vue'

//Lista com os herois
const heroes_source = [
    { name: 'ANTIMAGE', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/antimage.png", type:"a" },
    { name: 'ARC WARDEN', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/arc_warden.png", type:"a" },
    { name: 'AXE', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/axe.png", type:"s" },
    { name: 'BANE', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bane.png", type:"i" },
    { name: 'BATRIDER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/batrider.png", type:"i"  },
    { name: 'BEASTMASTER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/beastmaster.png", type:"s"  },
    { name: 'BLOODSEEKER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bloodseeker.png", type:"a"  },
    { name: 'BOUNTY_HUNTER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bounty_hunter.png", type:"i"  },
    { name: 'BREWMASTER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/brewmaster.png", type:"a"  },
    { name: 'BRISTLEBACK', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bristleback.png", type:"a"  },
    { name: 'BROODMOTHER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/broodmother.png", type:"i"  },
    { name: 'CENTAUR', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/centaur.png", type:"a"  },
    { name: 'ABADDON', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/abaddon.png", type:"a"  },
    { name: 'ANCIENT APPARITION', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ancient_apparition.png", type:"a"  },
    { name: 'CHAOS_KNIGHT', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/chaos_knight.png", type:"a"  },
    { name: 'CHEN', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/chen.png", type:"a"  },
    { name: 'CLINKZ', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/clinkz.png", type:"a"  },
    { name: 'RATTLETRAP', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/rattletrap.png", type:"a"  },
    { name: 'CRYSTAL MAIDEN', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/crystal_maiden.png", type:"i"  },
    { name: 'DARK SEER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dark_seer.png", type:"a"  },
    { name: 'DARK WILLOW', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dark_willow.png", type:"a"  },
    { name: 'DAWNBREAKER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dawnbreaker.png", type:"a"  },
    { name: 'DAZZLE', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dazzle.png", type:"a"  },
    { name: 'DEATH PROPHET', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/death_prophet.png", type:"a"  },
    { name: 'DISRUPTOR', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/disruptor.png", type:"a"  },
    { name: 'DOOM BRINGER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/doom_bringer.png", type:"a"  },
    { name: 'DRAGON KNIGHT', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dragon_knight.png", type:"a"  },
    { name: 'DROW RANGER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/drow_ranger.png", type:"a"  },
    { name: 'EARTH SPIRIT', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/earth_spirit.png", type:"a"  },
    { name: 'EARTHSHAKER', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/earthshaker.png", type:"a"  },
    { name: 'ELDER TITAN', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/elder_titan.png", type:"a"  },
    { name: 'EMBER SPIRIT', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ember_spirit.png", type:"a"  },
    { name: 'ENCHANTRESS', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/enchantress.png', type:"a" },
    { name: 'ENIGMA', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/enigma.png', type:"a" },
    { name: 'FACELESS_VOID', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/faceless_void.png', type:"a" },
    { name: 'GRIMSTROKE', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/grimstroke.png', type:"a" },
    { name: 'GYROCOPTER', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/gyrocopter.png', type:"a" },
    { name: 'HOODWINK', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/hoodwink.png', type:"a" },
    { name: 'HUSKAR', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/huskar.png', type:"a" },
    { name: 'INVOKER', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/invoker.png', type:"a" },
    { name: 'WISP', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/wisp.png', type:"a" },
    { name: 'JAKIRO', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/jakiro.png', type:"a" },
    { name: 'JUGGERNAUT', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/juggernaut.png', type:"a" },
    { name: 'KEEPER_OF_THE_LIGHT', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/keeper_of_the_light.png', type:"a" },
    { name: 'KUNKKA', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/kunkka.png', type:"a" },
    { name: 'LEGION_COMMANDER', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/legion_commander.png', type:"a" },
    { name: 'LESHRAC', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/leshrac.png', type:"a" },
    { name: 'LICH', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lich.png', type:"a" },
    { name: 'LIFE STEALER', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/life_stealer.png', type:"a" },
    { name: 'LINA', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lina.png', type:"a" },
    { name: 'LION', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lion.png', type:"a" },
    { name: 'LONE DRUID', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lone_druid.png', type:"a" },
    { name: 'LUNA', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/luna.png', type:"a" },
    { name: 'LYCAN', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lycan.png', type:"a" },
    { name: 'MAGNATAUR', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/magnataur.png', type:"a" },
    { name: 'MARS', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/mars.png', type:"a" },
    { name: 'MEDUSA', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/medusa.png', type:"a" },
    { name: 'MEEPO', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/meepo.png', type:"a" },
    { name: 'MIRANA', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/mirana.png', type:"a" },
    { name: 'MONKEY KING', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/monkey_king.png', type:"a" },
    { name: 'MORPHLING', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/morphling.png', type:"a" },
    { name: 'NAGA SIREN', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/naga_siren.png', type:"a" },
    { name: 'FURION', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/furion.png', type:"a" },
    { name: 'NECROLYTE', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/necrolyte.png', type:"a" },
    { name: 'NIGHT STALKER', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/night_stalker.png', type:"a" },
    { name: 'NYX ASSASSIN', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/nyx_assassin.png', type:"a" },
    { name: 'OGRE MAGI', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ogre_magi.png', type:"a" },
]
//--------------------------------------------


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
            return array
        },
        width_row: function(){
            const with_hero = 225
            const quant_heroes_row = heroes_source.length / 3
            return `${quant_heroes_row * with_hero}px`
        }
    }
}
</script>

<style lang="scss" scoped>
.grid-herois {
    background-color: black;
    height: 800px;
    overflow: hidden;
    background-position: repeat-x;
    & > div {
        display: flex;
        justify-content: left;
        align-items: center;
        gap: 10px;
        height: 175px; // Definir a altura proxima ao dos blocos dos herois obriga ele à ficar em uma unica linha, com overflow fora da tela
    }
    .grid-line {
        animation: moveSlideshow 10s linear infinite; 
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
        transform: translateX(-100%);  
    }
}

</style>

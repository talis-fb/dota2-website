<template>
    <section class="grid-herois">
        <div>
            <Hero 
             v-for="(i) of third_heroes(1)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i" 
             />
        </div>
        <div>
            <Hero 
             v-for="(i) of third_heroes(2)" 
             :type="i.type"
             :name="i.name"
             :img="i.img"  
             :key="i" 
             />
        </div>
        <div>
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
    { name: 'antimage', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/antimage.png", type:"a" },
    { name: 'arc_warden', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/arc_warden.png", type:"a" },
    { name: 'axe', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/axe.png", type:"s" },
    { name: 'bane', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bane.png", type:"i" },
    { name: 'batrider', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/batrider.png", type:"i"  },
    { name: 'beastmaster', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/beastmaster.png", type:"s"  },
    { name: 'bloodseeker', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bloodseeker.png", type:"a"  },
    { name: 'bounty_hunter', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bounty_hunter.png", type:"i"  },
    { name: 'brewmaster', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/brewmaster.png", type:"a"  },
    { name: 'bristleback', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bristleback.png", type:"a"  },
    { name: 'broodmother', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/broodmother.png", type:"i"  },
    { name: 'centaur', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/centaur.png", type:"a"  },
    { name: 'abaddon', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/abaddon.png", type:"a"  },
    { name: 'ancient_apparition', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ancient_apparition.png", type:"a"  },
    { name: 'chaos_knight', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/chaos_knight.png", type:"a"  },
    { name: 'chen', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/chen.png", type:"a"  },
    { name: 'clinkz', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/clinkz.png", type:"a"  },
    { name: 'rattletrap', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/rattletrap.png", type:"a"  },
    { name: 'crystal_maiden', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/crystal_maiden.png", type:"i"  },
    { name: 'dark_seer', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dark_seer.png", type:"a"  },
    { name: 'dark_willow', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dark_willow.png", type:"a"  },
    { name: 'dawnbreaker', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dawnbreaker.png", type:"a"  },
    { name: 'dazzle', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dazzle.png", type:"a"  },
    { name: 'death_prophet', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/death_prophet.png", type:"a"  },
    { name: 'disruptor', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/disruptor.png", type:"a"  },
    { name: 'doom_bringer', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/doom_bringer.png", type:"a"  },
    { name: 'dragon_knight', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dragon_knight.png", type:"a"  },
    { name: 'drow_ranger', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/drow_ranger.png", type:"a"  },
    { name: 'earth_spirit', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/earth_spirit.png", type:"a"  },
    { name: 'earthshaker', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/earthshaker.png", type:"a"  },
    { name: 'elder_titan', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/elder_titan.png", type:"a"  },
    { name: 'ember_spirit', img:"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ember_spirit.png", type:"a"  },
    { name: 'enchantress', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/enchantress.png', type:"a" },
    { name: 'enigma', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/enigma.png', type:"a" },
    { name: 'faceless_void', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/faceless_void.png', type:"a" },
    { name: 'grimstroke', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/grimstroke.png', type:"a" },
    { name: 'gyrocopter', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/gyrocopter.png', type:"a" },
    { name: 'hoodwink', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/hoodwink.png', type:"a" },
    { name: 'huskar', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/huskar.png', type:"a" },
    { name: 'invoker', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/invoker.png', type:"a" },
    { name: 'wisp', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/wisp.png', type:"a" },
    { name: 'jakiro', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/jakiro.png', type:"a" },
    { name: 'juggernaut', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/juggernaut.png', type:"a" },
    { name: 'keeper_of_the_light', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/keeper_of_the_light.png', type:"a" },
    { name: 'kunkka', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/kunkka.png', type:"a" },
    { name: 'legion_commander', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/legion_commander.png', type:"a" },
    { name: 'leshrac', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/leshrac.png', type:"a" },
    { name: 'lich', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lich.png', type:"a" },
    { name: 'life_stealer', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/life_stealer.png', type:"a" },
    { name: 'lina', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lina.png', type:"a" },
    { name: 'lion', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lion.png', type:"a" },
    { name: 'lone_druid', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lone_druid.png', type:"a" },
    { name: 'luna', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/luna.png', type:"a" },
    { name: 'lycan', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/lycan.png', type:"a" },
    { name: 'magnataur', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/magnataur.png', type:"a" },
    { name: 'mars', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/mars.png', type:"a" },
    { name: 'medusa', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/medusa.png', type:"a" },
    { name: 'meepo', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/meepo.png', type:"a" },
    { name: 'mirana', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/mirana.png', type:"a" },
    { name: 'monkey_king', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/monkey_king.png', type:"a" },
    { name: 'morphling', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/morphling.png', type:"a" },
    { name: 'naga_siren', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/naga_siren.png', type:"a" },
    { name: 'furion', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/furion.png', type:"a" },
    { name: 'necrolyte', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/necrolyte.png', type:"a" },
    { name: 'night_stalker', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/night_stalker.png', type:"a" },
    { name: 'nyx_assassin', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/nyx_assassin.png', type:"a" },
    { name: 'ogre_magi', img: 'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ogre_magi.png', type:"a" },
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
        }
    }
}
</script>

<style lang="scss" scoped>
.grid-herois {
    height: 800px;
    & > div {
        display: flex;
        overflow: hidden;
        flex-wrap: nowrap;
    }
}
</style>

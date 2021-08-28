<template>
	<section class="grid-herois">
		<Hero 
			v-for="i of heroes_source" 
			:type="i.type"
			:name="i.name"
			:img="i.img"  
			:key="i" 
		/>
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
}
</script>

<style lang="scss" scoped>
.grid-herois {
	height: 800px;
}
</style>

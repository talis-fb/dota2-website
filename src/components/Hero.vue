<template>
	<a class="hero"  href="/">
		<img class="hero-photo" v-bind:src="heroes_source[3]" alt="">
		<div class="label">
			<img :src="atributos_source[0]" height="10px" alt="">
			<span>{{ name }}</span>
		</div>
	</a>
</template>

<script>

const atributos_source = [
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_intelligence.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_agility.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png"
]

const heroes_source = [
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/antimage.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/arc_warden.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/axe.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bane.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/batrider.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/beastmaster.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bloodseeker.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bounty_hunter.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/brewmaster.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/bristleback.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/broodmother.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/centaur.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/abaddon.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/abaddon.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ancient_apparition.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/chaos_knight.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/chen.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/clinkz.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/rattletrap.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/crystal_maiden.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dark_seer.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dark_willow.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dawnbreaker.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dazzle.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/death_prophet.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/disruptor.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/doom_bringer.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/dragon_knight.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/drow_ranger.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/earth_spirit.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/earthshaker.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/elder_titan.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/ember_spirit.png"
]

export default {
	name: 'Hero',
	props: [ 'name'],
	data: () => {
		return {
			atributos_source,
			heroes_source
		}
	},
}
</script>

<style lang="scss" scoped>
.hero {
	height: 127px;
	width: 225px;
	position: relative;
	display: inline-block;
	transition: ease 0.3s;

	.hero-photo {
		position: absolute;
		width: 100%;
		height: 100%;
		left: 0;
		top:0;
	}
	.label {
		position: relative;
		z-index: 1;
		height: 100%;
		padding: 5px;
		font-size: 18px;
		display: none;
	}

	&:hover {
		z-index: 5;
		transform: scale(1.25);
		.label {
			display: flex;
			align-items: flex-end;
			img {
				width: 45px;
				height: 45px;
			}
		}
	}
}
</style>

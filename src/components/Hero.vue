<template>
	<a class="hero"  href="/">
		<img class="hero-photo" v-bind:src="img || sem_imagem" alt="">
		<div class="label">
			<div class="content">
				<img :src="return_atb_src(type) || sem_atb" height="10px" alt="">
				<span>{{ name }}</span>
			</div>
		</div>
	</a>
</template>

<script>

const atributos_source = [
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_intelligence.png",
	"https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_agility.png",
]

export default {
	name: 'Hero',
	props: [ 'name', 'img', 'type'],
	data: () => {
		return {
			sem_imagem: "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/antimage.png",
			sem_atb: "https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png",
			return_atb_src: function(atb){
				if( atb=="s" ) return atributos_source[0]
				if( atb=="i" ) return atributos_source[1]
				if( atb=="a" ) return atributos_source[2]
				return ''
			}
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
		img {
			width: 35px;
			height: 35px;
		}
		position: absolute;
		width: 100%;
		z-index: 1;
		bottom: 0;
		transform: translateY(30px);
		padding: 5px;
		font-size: 18px;
		opacity: 0;
		transition: ease 0.2s;

		.content{
			display: flex;
			align-items: center;
			gap: 5px;
		}
	}

	&:hover {
		z-index: 5;
		transform: scale(1.25);
		.label {
			transform: translateY(0px);
			bottom: 0;
			opacity: 1;
		}
	}
}
</style>

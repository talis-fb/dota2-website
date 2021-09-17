<template>
	<section class="herois">
		<img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/home/heroes_full.jpg" alt="">
		<div class="content">
			<h1>QUEM VOCÊ ESCOLHERÁ?</h1>
			<div class="divisor"></div>
			<h3>De engenhosos magos a brutamontes destemidos, passando por rebeldes astutos, a gama de heróis do Dota 2 é enorme e incrivelmente diversa. Lance habilidades incríveis e Ultimates devastadoras no seu caminho para a vitória.</h3>
			<a href="/"> VER TODOS OS HERÓIS </a>
		</div>
	</section>
</template>

<script>
//import GridHeroes from './Sec_grid_heroes.vue'

export default {
	name: 'App',
	components: {
	}
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Laila:wght@500&display=swap');
@import '../global';

.herois {
    background-color: black;
	position: relative;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;

	img {
		width: 100%;
		max-width: 1600px;
	}

	.content{
		position: absolute;
		bottom: 0px;
		width: 1000px;
		align-self: center;
		max-width: 50%;
		background-color: none;

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap:10px;

		h1{
			color: white;
			font-size: 70px;
		}
		h3 {
			color:white;
			font-size: 14pt;
		}
		a{
            @include botao;
            text-align: center;
            padding: 10px;
            font-size: 20pt;
		}
	}
}
</style>

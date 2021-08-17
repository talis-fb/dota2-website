<template>
	<section class="herois">
		<img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react//home/heroes_full.jpg" alt="">
		<div>
			<h1>Quem você escolherá?</h1>
			<span>De engenhosos magos a brutamontes destemidos, passando por rebeldes astutos, a gama de heróis do Dota 2 é enorme e incrivelmente diversa. Lance habilidades incríveis e Ultimates devastadoras no seu caminho para a vitória.</span>
			<a href="/">
				Ver todos os heróis
			</a>
		</div>
	</section>
</template>

<script>

export default {
	name: 'App',
	components: {
	}
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Laila:wght@500&display=swap');

.herois {
	position: relative;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;

	& > div {
		position: absolute;
		bottom: 0px;
		width: 1000px;
		align-self: center;
	}

	//background-image: url("https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/deaae2bcc11b7ef6963ade2793e8f619ed20546a.jpg");
	//background-repeat: no-repeat;
	//background-size: cover;
	//background-position: center;
	background-color: grey;
	img {
		width: 100%;
		max-width: 1600px;
	}
	a{
		color: white;
		display: flex;
		align-items: center;
		padding: 5px;
		border: 3px solid grey;
		border-radius: 10px;
		h3{
			color: white;
			text-decoration:none;
			text-decoration-line: none;
		}
		h4{
			color:grey;
		}
		img{
			width:25%;
		}
		&:hover{
			border-color: orangered;
			transition-duration: 0.2s;
			transform: translateY(-3px);
		}
	}
}
</style>

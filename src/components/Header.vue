<template>
	<header>
		<nav class="nav-items">
			<img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/global/dota2_logo_horiz.png" alt="Dota 2">
			<a href="">Jogo</a>
			<a href="">Heróis</a>
			<a href="">Novidades</a>
		</nav>
		<nav class="options">
			<div>
				<span>INICIAR SESSÃO</span>
				<span>SELECIONAR IDIOMA</span>
			</div>
			<a href="https://store.steampowered.com/app/570/Dota_2/">
				<img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react//icons/steam.svg" alt="">
				JOGUE GRATUITAMENTE
			</a>
		</nav> 
	</header>
</template>

<script>
export default {
	
}
</script>

<style lang="scss" scoped>
header{
	position: absolute;
	top:0;
	z-index:1;
	display: flex;
	justify-content: space-between;
	height: 80px;
	width: 100%;
	//background-color: red;
	padding: 7px;
	font-family: 'Laila', sans-serif;
}

.nav-items{
	display: flex;
	align-items: center;
	gap: 20px;
	font-size: 20pt;
	color: white;
	img{
		//height: 100%;
	}
	a {
		color: white;
	}
}
.options{
	display: flex;
	align-items: center;
	gap: 20px;
	color: white;

	div {
		display: flex;
		flex-direction: column;
		align-items: flex-end;
	}

	a{
		color: white;
		display: flex;
		align-items: center;
		padding: 5px;
		border: 3px solid grey;
		border-radius: 10px;
		&:hover{
			border-color: orangered;
			transition-duration: 0.2s;
			transform: translateY(-3px);
		}
	}
}

video {
	width:100%;
	top:0;
}
</style>

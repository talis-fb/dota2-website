<template>
	<header>
		<nav class="nav-items">
			<a href="/"><img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/global/dota2_logo_horiz.png" alt="Dota 2"></a>
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
	display: flex;
	z-index:1;
	justify-content: space-between;
}

.nav-items{
	display: flex;
}
.options{
	display: flex;
}

.welcome-screen{
	position: relative;
}

video {
	width:100%;
	top:0;
}
</style>

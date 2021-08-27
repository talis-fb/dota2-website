<template>
	<section >
		<div class="video-background">
			<video type="video/mp4" autoplay src="https://cdn.cloudflare.steamstatic.com/apps/dota2/videos/dota_react/homepage/dota_montage_02.mp4"></video>
		</div>

		<div class="label">
			<div class="main">
				“A Modern Multiplayer Masterpiece.”
			</div>
			<div class="divisor"></div>
			<a href="https://store.steampowered.com/app/570/Dota_2/">
				<img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react//icons/steam.svg" alt="">
				<div>
					<h3>PLAY FOR FREE</h3>
					<h4>DOWNLOAD ON STEAM</h4>
				</div>
			</a>
		</div>
	</section>
</template>

<script>
export default {
	
}
</script>

<style lang="scss" scoped>

section {
	position: relative;
	height: 100%;
	.label{
		font-family: 'Laila', sans-serif;
		top: 0;
		position: absolute;
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 30px;
		align-content: left;
		margin-left: 100px;
		height:100%;
		max-width: 60%;

		font-size: 60px;
		color: white;
		z-index:1;

		.main {
			text-align: left;
		}

		.divisor{
			width: 80px;
			height:5px;
			background-color: rgb(162, 23, 0);
		}

		a{
			width: 401px;
			height: 78px;
			color: white;
			display: flex;
			align-items: center;
			padding: 5px;
			border: 3px solid grey;
			border-radius: 10px;
			h3{
				font-size: 22px;
				color: white;
				text-decoration:none;
				text-decoration-line: none;
			}
			h4{
				font-size: 15px;
				color:grey;
			}
			img{
				width:25%;
				width: 48px;
				height: 48px;
			}
			&:hover{
				border-color: orangered;
				transition-duration: 0.2s;
				transform: translateY(-3px);
			}
		}

	}
}

video {
	width:100%;
	top:0;
}
</style>

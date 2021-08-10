<template>
	<section >
		<div class="video-background">
			<video type="video/mp4" autoplay src="https://cdn.cloudflare.steamstatic.com/apps/dota2/videos/dota_react/homepage/dota_montage_02.mp4"></video>
		</div>

		<div class="label">
			<div>
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
@import url('https://fonts.googleapis.com/css2?family=Laila:wght@500&display=swap');

section {
	position: relative;
	.label{
		font-family: 'Laila', sans-serif;
		position: absolute;
		color: blue;
		font-size: 50pt;
		z-index:1;

		.divisor{
			width: 80px;
			height:5px;
			background-color: rgb(162, 23, 0);
		}

		a{
			margin-top: 10px;
			display: flex;
			justify-content: space-around;
			background: none;
			text-align: left;
			border: 2px solid grey;
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
		}
	}
}

video {
	width:100%;
	top:0;
}
</style>

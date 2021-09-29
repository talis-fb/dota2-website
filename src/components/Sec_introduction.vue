<template>
	<section class="intro">
		<div class="video-background">
			<video type="video/mp4" autoplay loop muted src="https://cdn.cloudflare.steamstatic.com/apps/dota2/videos/dota_react/homepage/dota_montage_02.mp4"></video>
		</div>

		<div class="label" :style="style_title">
			<div class="main">
				"A MODERN MULTIPLAYER MASTERPIECE."
			</div>
			<div class="divisor"></div>
			<a href="https://store.steampowered.com/app/570/Dota_2/" target="_blank" >
				<img src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react//icons/steam.svg" alt="">
				<div>
					<h3>PLAY FOR FREE</h3>
					<h4>DOWNLOAD ON STEAM</h4>
				</div>
			</a>
		</div>

        <div class="shadow-layer"></div>
	</section>
</template>

<script>
export default {
    name: 'title',
    data: function(){
        return {
            state_visibility_title: false
        }
    },
    computed: {
        style_title: function(){
            return this.state_visibility_title ? { opacity: 1, transform: 'translateX(30px)' } : { opacity: 0, transform: 'translateX(0px)' }
        }
    },
    mounted: function(){
        let titulo_animado = document.querySelector('.intro > .label')
        const callback = (e) => this.state_visibility_title = !!e[0].isIntersecting // Retorna um booleano, que esta relacionado se o está na tela atual
        let observer = new IntersectionObserver(callback, { threshold: [0.5] }) // Observador
        observer.observe(titulo_animado);
    }
}
</script>

<style lang="scss" scoped>
@import '../_global.scss';
section {

    .shadow-layer{
        position: absolute;
        width: 100%;
        height: 400px;
        bottom: 0;
        background: -webkit-gradient(linear, left top, left bottom, color-stop(60%, rgba(0, 0, 0, 0)), color-stop(80%, rgba(0, 0, 0, 0.7)), color-stop(100%, black));
    }
    

	position: relative;
	height: 100%;
	.label{
        transition: ease 1.5s;
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
            @include divisor;
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
    opacity: 0.6;
}
</style>

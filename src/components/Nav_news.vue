<template>
	<section class="sections-news">
		<section class="news">
			<header>
				<span class="title">Últimas Noticias</span>
				<span class="sub-title">Ver todas </span>
			</header>
			<main>
				<div class="bloco-new">
					<div class="content">
						<h3>5 de agosto de 2021</h3>
						<h2>Pacote de Nível de Batalha</h2>
						<div class="detalhes">
							<span>O Pacote de Nível de Batalha do Nemestício de 2021 chegou, trazendo a oportunidade para portadores do passe de batalha avançarem mais a fundo na lista de recompensas com um grande...</span>
						</div>
					</div>
				</div>
				<div class="bloco-new">
					<div class="content">
						<h3>5 de agosto de 2021</h3>
						<h2>Pacote de Nível de Batalha</h2>
						<div class="detalhes">
							<span>O Pacote de Nível de Batalha do Nemestício de 2021 chegou, trazendo a oportunidade para portadores do passe de batalha avançarem mais a fundo na lista de recompensas com um grande...</span>
						</div>
					</div>
				</div>
				<div class="bloco-new">
					<div class="content">
						<h3>5 de agosto de 2021</h3>
						<h2>Pacote de Nível de Batalha</h2>
						<div class="detalhes">
							<span>O Pacote de Nível de Batalha do Nemestício de 2021 chegou, trazendo a oportunidade para portadores do passe de batalha avançarem mais a fundo na lista de recompensas com um grande...</span>
						</div>
					</div>
				</div>
			</main>
		</section>
	</section>
</template>

<script>
//<img src="https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/deaae2bcc11b7ef6963ade2793e8f619ed20546a.jpg" alt="">
</script>

<style lang="scss" scoped>
.sections-news{
	background-color: black;
	padding-top: 30px;
	padding-bottom: 30px;
	.news{
		background-color: black;
		width: 1200px;
		margin: 0 auto;
		color: white;
		header {
			display: flex;
			align-items: center; 
			gap: 15px;
			margin-bottom: 10px;
			font-size: 15pt;
			.title{
				font-weight: bolder;
			}
			.sub-title{
				font-weight: normal;
				transition: 0.1s;
				&:hover{
					font-size: 18pt;
				}
			}
		}
		main {
			display: flex;
			justify-content: space-between;

			.bloco-new {
				height: 245px;
				width: 370px;
				background-image: url("https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/deaae2bcc11b7ef6963ade2793e8f619ed20546a.jpg");
				background-repeat: no-repeat;
				background-size: cover;
				background-position: center;
				.content{
					height: 100%;
					width: 100%;
					display: flex;
					flex-direction: column;
					justify-content: flex-end;
					transition: 0.3s;
					.detalhes{
						display: none;
					}
					&:hover{
						border-bottom: 3px solid red;
						.detalhes{
							display: block;
						}
					}
				}
			}
		}

	}
}

</style>

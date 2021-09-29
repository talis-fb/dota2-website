<template>
    <section class="sections-news">
        <section class="news">
            <header>
                <span class="title">Últimas Noticias</span>
                <span class="sub-title">Ver todas </span>
            </header>
            <main>

                <div class="bloco-new" :style="{ 'background-image': `url(${n.img})` }" 
                     v-for="n of news" :key="n.title" >
                     <div class="content">
                         <h3>{{ n.date }}</h3>
                         <h2>{{ n.title }}</h2>
                         <div class="detalhes">
                             <span>{{ n.content }}</span>
                         </div>
                         <div class="shadow-layer"></div>
                     </div>
                </div> 

			</main>
		</section>
	</section>
</template>

<script>
//<img src="https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/deaae2bcc11b7ef6963ade2793e8f619ed20546a.jpg" alt="">

export default {
    name: 'App',
    data: function(){
        return { 
            news: [ { 
                img: 'https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/aaa99b58717192fd28e828ac3f2962c2c9357587.jpg', 
                title: 'O International está chegando', date: '16 de setembro de 2021',  content: 'Estamos felizes de anunciar que, depois de muita consideração, a venda de ingressos para assistir ao evento principal do International 2021 presencialmente em Bucareste na...'
            },{
                img: 'https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/8fb4c8928c49a685500fa625bfcd518a082c983c.png',
                title: 'Venda de ingressos para o International 2021', date: '3 de setembro de 2021',  content: 'Até que enfim, as melhores equipes de Dota do mundo se reunirão em outubro para travar a décima batalha pela Égide dos Campeões.'
            },{
                img: 'https://cdn.cloudflare.steamstatic.com/steamcommunity/public/images/clans/3703047/22b89b3523cfa585881e29d773ef8fbd87d22ee0.jpg', 
                title: 'Atualização do Dota+ do outono de 2021', date: '1 de setembro de 2021',  content: 'O sol do verão começa a se distanciar dos terrenos do Dota, abrindo caminho para o outono e avisando aos smeevils que chegou a hora de mais uma atualização sazonal para o Dota+.'
            }]
        }
    }
}
</script>

<style lang="scss" scoped>
.sections-news{
	.news{
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

                border-bottom: 3px solid grey;
                transition: ease 0.2s;
                &:hover {
                    transform: scale(1.03);
                    border-bottom: 6px solid #ff6046;
                }

				.content{
                    position: relative;
                    .shadow-layer {
                        position: absolute;
                        background: rgba(0, 0, 0, 0) linear-gradient(rgba(19, 23, 28, 0) 60%, rgba(19, 23, 28, 0.733) 70%, rgb(19, 23, 28) 90%) repeat scroll 0% 0%;
                        width: 100%;
                        height: 100%;
                        bottom: 0;
                        left: 0;
                        right: 0;
                        z-index: 0;
                    }
                    & > * {
                        z-index: 1;
                    }
                    padding: 10px;
                    text-align: left;
					height: 100%;
					width: 100%;
					display: flex;
					flex-direction: column;
					justify-content: flex-end;
					transition: ease 0.3s;
					.detalhes{
						display: none;
					}
					&:hover{
                        background: rgba(0,0,0,.7);
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

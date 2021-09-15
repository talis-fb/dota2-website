<template>
	<Header />
	<Introduction />
	<NavNews />
	<SecHeroes />
	<GridHeroes />
    <FinalSection />
    <Footer />
</template>

<script>
import Header from './components/Header.vue'
import Introduction from './components/Sec_introduction.vue'
import NavNews from './components/Nav_news.vue'
import SecHeroes from './components/Sec_heroes.vue'
import GridHeroes from './components/Sec_grid_heroes.vue'
import Footer from './components/Footer.vue'
import FinalSection from './components/Sec_final.vue'

export default {
	name: 'App',
	components: {
		Header,
		Introduction,
		NavNews,
		SecHeroes,
		GridHeroes,
        FinalSection,
        Footer,
	}
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Laila:wght@500&display=swap');
@import './global';

/*
Fontes :
	'Acme' 
	'Vollkorn' 
	'Alegreya' */
@import url('https://fonts.googleapis.com/css2?family=Acme&family=Alegreya:wght@400;500&family=Vollkorn:wght@400;500&display=swap');
/********/

*{
	margin: 0;
	border:0;
	box-sizing: border-box;
	text-decoration:none;
	color: white;
	font-family: $font, sans-serif;
}
#app {
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}
</style>

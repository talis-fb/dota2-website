<template>
	<Header />
	<Introduction />
	<NavNews />
	<SecHeroes />
	<GridHeroes />
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Introduction from './components/Sec_introduction.vue'
import NavNews from './components/Nav_news.vue'
import SecHeroes from './components/Sec_heroes.vue'
import GridHeroes from './components/Sec_grid_heroes.vue'

export default {
	name: 'App',
	components: {
		//HelloWorld,
		Header,
		Introduction,
		NavNews,
		SecHeroes,
		GridHeroes
	}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Laila:wght@500&display=swap');
*{
	margin: 0;
	border:0;
	box-sizing: border-box;
	text-decoration:none;
	color: white;
	font-family: 'Laila', sans-serif;
}
#app {
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}
</style>

<template>
	<section class="grid-herois">
		<Hero name="Heroi" />
		<Hero name="Heroi" />
		<Hero name="Heroi" />
		<Hero name="Heroi" />
		<Hero name="Heroi" />
		<Hero name="Heroi" />
	</section>
</template>

<script>
import Hero from './Hero.vue'

export default {
	name: 'App',
	components: {
		Hero
	}
}
</script>

<style lang="scss" scoped>
.grid-herois {
	height: 800px;
}
</style>

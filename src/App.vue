<template>
	<div>
		<TheNa></TheNa>
		<TheView></TheView>
	</div>
</template>

<script>
import TheNa from './components/TheNav.vue';
import TheView from './components/TheView.vue';
export default {
	components: {
		TheNa,
		TheView,
	},
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>

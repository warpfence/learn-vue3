<template>
	<main>
		<LifecycleHook></LifecycleHook>
	</main>
</template>

<script>
import LifecycleHook from './LifecycleHook.vue';
export default {
	components: {
		LifecycleHook,
	},
	setup() {
		console.log('setup');
		return {};
	},
};
</script>

<style lang="scss" scoped></style>

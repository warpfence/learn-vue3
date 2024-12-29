<template>
	<div>
		<button class="btn btn-primary" type="button" @click="sayHello">
			My button
		</button>
	</div>
</template>

<script>
export default {
	setup(props, { emit }) {
		const sayHello = () => {
			emit('sayHello');
		};
		return { sayHello };
	},
};
</script>

<style lang="scss" scoped></style>

<template>
	<div></div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		const count = ref(0);
		const state = reactive({
			count: count,
		});
		count.value++;
		count.value++;
		// console.log(count.value);
		// console.log('state.count: ', state.count);

		// ref -> Array
		const message = ref('Hello');
		const arr = reactive([message]);
		console.log('arr[0]: ', arr[0].value);

		return {
			count,
			state,
		};
	},
};
</script>

<style lang="scss" scoped></style>

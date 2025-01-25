<template>
	<div>
		<button class="btn btn-primary" type="button" @click="sayHello">
			My button {{ message }}
		</button>
	</div>
</template>

<script>
export default {
	inheritAttrs: false,
};
</script>

<script setup>
import { ref } from 'vue';

const emit = defineEmits('sayHello');
const sayHello = () => {
	emit('sayHello');
};
const message = ref('message');
</script>

<style lang="scss" scoped></style>

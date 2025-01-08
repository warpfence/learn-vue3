<template>
	<div class="card">
		<div class="card-header">
			<slot v-if="$slots.header" name="header" header-message="헤더메시지"
				>#Header</slot
			>
		</div>
		<div class="card-body">
			<slot :child-message="childMessage" hello-message="안녕하세요"
				>#Body</slot
			>
		</div>
		<div class="card-footer text-body-secondary">
			<slot v-if="hasFooter" name="footer" footer-message="푸터메시지"
				>#Footer</slot
			>
		</div>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup(props, { slots }) {
		const childMessage = ref('자식컴포넌트메시지');
		const hasFooter = computed(() => !!slots.footer);
		return { childMessage, hasFooter };
	},
};
</script>

<style lang="scss" scoped></style>

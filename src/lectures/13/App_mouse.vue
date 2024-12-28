<template>
	<div>
		<div id="modifiers">
			<div @click="clickDiv">
				DIV 영역
				<p @click="clickP">
					P 영역
					<!-- <span @click.stop="clickSpan">SPAN 영역</span> -->
					<span @click="clickSpan">SPAN 영역</span>
					<a href="https://naver.com" @click.prevent.stop="clickA">a 영역</a>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	setup() {
		const clickDiv = () => {
			console.log('ClickDiv');
		};
		const clickP = () => {
			console.log('ClickP');
		};
		const clickSpan = () => {
			console.log('ClickSpan');
		};
		const clickA = () => {
			alert('어떤기능~');
		};
		return {
			clickDiv,
			clickP,
			clickSpan,
			clickA,
		};
	},
};
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
	padding: 40px;
}
#modifiers div {
	background-color: #ccc;
}
#modifiers p {
	background-color: #999;
}
#modifiers span {
	background-color: #666;
}
</style>

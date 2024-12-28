<template>
	<div>
		<h2>input value</h2>
		<!-- <input type="text" v-model.lazy="inputvalue" /> -->
		<!-- <input type="text" v-model.number="inputvalue" /> -->
		<input type="text" v-model.trim="inputvalue" />
		<div>{{ inputvalue }}</div>
		<hr />
		<h2>textarea value</h2>
		<textarea v-model="textareaValue"></textarea>
		<div>{{ textareaValue }}</div>
		<hr />
		<h2>checkbox value</h2>
		<label for="checkbox">{{ checkboxValue }}</label>
		<input type="checkbox" id="checkbox" v-model="checkboxValue" />
		<!-- :checked="checkboxValue"
			@change="event => (checkboxValue = event.target.checked)" -->
		<hr />
		<h2>radio value</h2>
		<label>
			<input type="radio" name="type" value="O" v-model="radioValue" />
			O형
			<!-- :checked="radioValue === 'O'"
				@change="event => (radioValue = event.target.value)" -->
		</label>
		<label>
			<input type="radio" name="type" value="A" v-model="radioValue" />
			A형
			<!-- :checked="radioValue === 'A'"
				@change="event => (radioValue = event.target.value)" -->
		</label>
		<div>{{ radioValue }}</div>
	</div>
	<hr />
	<h2>select value</h2>
	<select v-model="selectValue">
		<option value="html">HTML 수업</option>
		<option value="css">CSS 수업</option>
		<option value="javascript">JavaScript 수업</option>
	</select>
	<div>{{ selectValue }}</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const inputvalue = ref('');
		const textareaValue = ref('');
		const checkboxValue = ref(true);
		const radioValue = ref('O');
		const selectValue = ref('html');
		return {
			inputvalue,
			textareaValue,
			checkboxValue,
			radioValue,
			selectValue,
		};
	},
};
</script>

<style lang="scss" scoped></style>

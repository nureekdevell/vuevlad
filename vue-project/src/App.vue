<template>
	<input v-model.lazy="firstName" type="text" />
	<p>{{ firstName }}</p>
	<br />
	<p>||||</p>
	<input v-model.trim="lastName" type="text" />
	<p>{{ lastName }}</p>

	<p>{{ visited.join(', ') }}</p>
	<select multiple v-model="visited">
		<option value="">Please select your Country</option>
		<option value="US">US</option>
		<option value="UZ">UZ</option>
		<option value="KZ">KZ</option>
		<option value="US">US</option>
		<option value="UZ">UZ</option>
		<option value="KZ">KZ</option>
	</select>
</template>

<script>
import { createApp } from 'vue';

export default {
	// data
	data() {
		return {
			firstName: '',
			lastName: '',
			country: '',
			visited: [],
		};
	},
	// method
	methods: {},

	beforeCreate() {
		console.log('beforCreate 1 ');
	},

	created() {
		console.log('Created');
	},

	beforeMount() {
		console.log('beforeMount');
	},
	mounted() {
		console.log('mounted');
	},
	beforeUpdate() {
		console.log('beforeUpdate');
	},
	updated() {
		console.log('updated');
	},

	beforeUnmount() {
		console.log('beforeUnmounted');
	},

	unmounted() {
		console.log('uchdi ');
	},

	computed: {
		// addNotes() {
		// 	console.log('double');
		// 	if (this.inputValue !== '') {
		// 		this.notes.push(this.inputValue);
		// 		this.inputValue = '';
		// 	}
		// },
	},
	watch: {
		inputValue(value) {
			if (value.length > 15) {
				this.inputValue = ' ';
			}
		},
	},
};
</script>

<style lang="scss" scoped></style>

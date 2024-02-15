<template>
	<div>
		<input
			v-model="inputValue"
			@keypress.enter="addNotes"
			type="text"
			placeholder="nimadur"
		/>
		<span v-for="(note, i) in notes" key="note">
			<li>
				{{ note }} {{ i + 1 }}
				<button class="" @click="remove(i)">Delete</button>
			</li></span
		>
		<h1
			:style="{
				color: inputValue.length <= 3 ? 'darkred' : 'darkblue',
			}"
		>
			Ismingiz 3 ta harfdan kop bolsin {{ double }}
		</h1>
		<button @click="increment">increment</button>
	</div>
</template>

<script>
import { createApp, handleError } from 'vue';

export default {
	// data
	data() {
		return {
			count: 0,
			notes: [],
			inputValue: '',
		};
	},
	// method
	methods: {
		increment() {
			this.count++;
		},
		addNotes() {
			if (this.inputValue !== '') {
				this.notes.push(this.inputValue);
				this.inputValue = '';
			}
		},

		remove(i) {
			this.notes.splice(i, 1);
		},
	},

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

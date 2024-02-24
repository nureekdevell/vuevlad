<template>
	<div>
		<input type="text" v-model="message" @keyup.enter="saveMessage" />
		<h2>Inner text</h2>
		<ul>
			<li v-for="person in peaple" :key="person">{{ person }}</li>
		</ul>
	</div>
</template>

<script>
export default {
	props: {
		peaple: {
			type: Array,
			reuired: true,
		},
	},
	data() {
		return {
			message: '',
		};
	},
	methods: {
		saveMessage: function () {
			this.$emit('message', this.message);
			this.message = '';
		},
	},
};
</script>

<style lang="scss" scoped></style>

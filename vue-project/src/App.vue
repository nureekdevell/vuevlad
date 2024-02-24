<template>
	<div>
		<List :peaple="peaple" @message="displayMessage" />
	</div>
</template>

<script>
import List from './components/List.vue';
export default {
	components: {
		List,
	},
	data() {
		return {
			peaple: ['Max', 'Jack', 'Leo'],
		};
	},
	methods: {
		displayMessage: function (message) {
			this.peaple.push(message);
		},
	},
};
</script>

<style scoped></style>

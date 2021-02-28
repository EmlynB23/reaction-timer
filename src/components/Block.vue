<template>
	<div v-if="showBlock">
		<div class="clickbox" @click="stopTimer">Click me!</div>
	</div>
</template>

<script>
export default {
	props: ["delay"],
	data() {
		return {
			showBlock: false,
			timer: null,
			reaction: 0,
		};
	},
	mounted() {
		setTimeout(() => {
			this.showBlock = true;
			this.startTimer();
		}, this.delay);
	},
	methods: {
		startTimer() {
			this.timer = setInterval(() => {
				this.reaction += 10;
			}, 10);
		},
		stopTimer() {
			clearInterval(this.timer);
			this.$emit("end", this.reaction);
		},
	},
};
</script>

<style>
.clickbox {
	background-color: green;
	color: #fff;
	border-radius: 10px;
	margin: 100px auto;
	padding: 50px;
	width: 400px;
}
</style>

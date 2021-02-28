<template>
	<div>
		<h3>Your score was {{ score }}</h3>
		<p v-if="score < 300">Rapid!</p>
		<p v-else-if="score < 400">Meh</p>
		<p v-else>You slow sack of shit</p>
	</div>
</template>

<script>
export default {
	props: ["score"],
};
</script>

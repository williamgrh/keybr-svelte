<script>
	import LessonSettings from '$lib/LessonSettings.svelte';
	import LiveScore from '$lib/LiveScore.svelte';
</script>

<svelte:head>
	<title>Typing Practice</title>
	<meta
		name="description"
		content="Take a typing test, practice typing lessons, learn to type faster."
	/>
</svelte:head>

<div class="practice">
	<LessonSettings />
	<LiveScore />
</div>

<style>
	.practice {
		margin: 2rem;
		max-width: 80rem;
		min-width: 60rem;
		position: relative;
	}
</style>

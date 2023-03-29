<script lang="ts">
	import type { Key } from '$types/Key.type';
	import KeysList from '$lib/KeysList.svelte';

	const keys: Key[] = [
		{ key: 'E', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'N', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'I', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'T', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'R', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'L', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'S', avgSpeed: 68, bestSpeed: 68, learningRate: 0, confidence: 1, boosted: false },
		{ key: 'A', avgSpeed: 68, bestSpeed: 68, learningRate: 343, confidence: 1, boosted: false },
		{
			key: 'U',
			avgSpeed: 13.1,
			bestSpeed: 13.1,
			learningRate: 134.918,
			confidence: 0.13,
			boosted: true
		},
		{ key: 'O', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'D', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'Y', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'C', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'H', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'G', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'M', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'P', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'B', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'K', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'V', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'W', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'F', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'Z', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'X', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'Q', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false },
		{ key: 'J', avgSpeed: 0, bestSpeed: 0, learningRate: 0, confidence: 0, boosted: false }
	];

	const currentKey = 'U';
</script>

<div class="live-score-container">
	<div class="score-section scores">
		<span class="score"
			><span class="title">Speed:</span>
			<span class="score-value">71.47</span> (<span class="delta positive">↑+7.92</span>)</span
		>
		<span class="score"
			><span class="title">Accuracy:</span>
			<span class="score-value">95.73</span> (<span class="delta positive">↑+0.48</span>)</span
		>
		<span class="score"
			><span class="title">Score:</span>
			<span class="score-value">1393.7</span> (<span class="delta negative">↓-860.1</span>)</span
		>
	</div>
	<div class="score-section keys">
		<KeysList {currentKey} {keys} />
	</div>
	<div class="current-key score-section" />
	<div class="daily-goal score-section" />
</div>

<style>
	.live-score-container {
		padding-top: 1rem;
	}

	.score-section {
		height: 2rem;
		border-bottom: 1px solid var(--color-separator);
		display: flex;
		align-items: center;
	}

	.scores {
		gap: 2rem;
	}

	.score {
		min-width: 10rem;
		display: inline-block;
	}

	.title {
		color: var(--color-section-title);
	}

	.score-value {
		margin-left: 0.2rem;
		color: var(--color-section-value);
		font-family: var(--font-monospace);
	}

	.delta {
		font-family: var(--font-monospace);
	}

	.delta.positive {
		color: var(--color-delta--positive);
	}

	.delta.negative {
		color: var(--color-delta--negative);
	}
</style>

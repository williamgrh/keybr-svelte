<script lang="ts">
	import type Key from '$types/Key.type';
	export let currentKey: string;
	export let keys: Key[];

	keys.map((key: Key) => {
		const title = `Character ${key.key}`;

		if (key.avgSpeed > 0 && key.bestSpeed > 0) {
			title.concat(
				`;\nAverage typing speed: ${key.avgSpeed}wpm;\nBest typing speed: ${key.bestSpeed}wpm`
			);
		} else {
			title.concat(';\nNot calibrated, need more samples');
		}

		if (key.confidence > 0) {
			title.concat(`;\nConfidence level: ${key.confidence}`);
		}

		if (key.learningRate > 0) {
			title.concat(`;\nLearning rate: ~${key.learningRate}wpm/hour`);
		}

		if (key.boosted) {
			title.concat(';\nA key with boosted frequency.');
		}

		key.title = title;

		if (key.confidence < 1 && key.confidence > 0) {
			const r = Math.floor((14 - 204) * key.confidence + 204);
			const g = Math.floor(218 * key.confidence);
			const b = Math.floor(97 * key.confidence);
			key.backgroundColor = `rgb(${r}, ${g}, ${b})`;
		}

		if (
			key.avgSpeed > 0 ||
			key.bestSpeed > 0 ||
			key.confidence > 0 ||
			key.learningRate > 0 ||
			key.boosted
		) {
			key.included = true;
		}
	});
</script>

<div class="keys" title="All keys in the otder of decreasing letter frequency.">
	<span class="keys-title">All keys:</span>
	<span class="keys-list">
		{#each keys as key}
			<span
				class="key"
				class:included={key.included}
				class:boosted={key.boosted}
				class:confident={key.confidence === 1}
				class:current={key.key === currentKey}
				style={key.backgroundColor ? `background-color: ${key.backgroundColor}` : ''}
				title={key.title}>{key.key}</span
			>
		{/each}
	</span>
</div>

<style>
	.keys {
		display: flex;
		align-items: center;
	}

	.keys-title {
		min-width: 8rem;
		display: inline-block;
		color: var(--color-section-title);
	}

	.keys-list {
		display: flex;
		flex: 1;
		align-items: center;
	}

	.key {
		font-family: var(--font-monospace);
		display: block;
		font-size: 0.9rem;
		height: 1.5rem;
		width: 1.5rem;
		line-height: calc(1.5rem - 2px);
		text-align: center;
		color: var(--color-key--uncalibrated__color);
		background-color: var(--color-key--uncalibrated__background);
		outline: 1px solid var(--color-key--uncalibrated__outline);
	}

	.key:not(:first-child) {
		margin-left: 1px;
	}

	.key.included {
		color: var(--color-key--included__color);
		background-color: var(--color-key--included__background);
		outline: 1px solid var(--color-key--included__outline);
	}

	.key.confident {
		background-color: var(--color-key--included__confident-background);
	}

	.key.boosted {
		color: var(--color-key--boosted__color);
		outline: 1px solid var(--color-key--boosted__outline);
	}
</style>

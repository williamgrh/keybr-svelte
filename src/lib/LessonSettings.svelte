<script>
	import HelpIcon from '$lib/images/help.svelte';
	import LeftArrowIcon from '$lib/images/left-arrow.svelte';
	import RightArrowIcon from '$lib/images/right-arrow.svelte';
	import ExpandInterfaceIcon from '$lib/images/expand-interface.svelte';
	import GearIcon from '$lib/images/gear.svelte';
</script>

<div class="lesson-settings">
	<button><HelpIcon /></button>
	<button><LeftArrowIcon /></button>
	<button><RightArrowIcon /></button>
	<button><ExpandInterfaceIcon /></button>
	<button class="settings-button"><GearIcon />Settings...</button>
</div>

<style>
	.lesson-settings {
		position: absolute;
		top: 0;
		right: 0;
	}

	.settings-button {
		background-color: var(--color-button-background);
		border-radius: 0.25rem;
		color: var(--color-button);
		padding: 0 1.5rem;
	}

	.settings-button :global(svg) {
		fill: var(--color-button);
	}
</style>

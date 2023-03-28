<script>
	import Sidenav from '$lib/Sidenav.svelte';
	import './styles.css';
</script>

<div class="app">
	<main>
		<slot />
	</main>

	<Sidenav />

	<div class="topbar" />
	<div class="sidebar" />
</div>

<style>
	.app {
		display: grid;
		min-height: 100vh;
		grid-template-areas:
			'topbar topbar topbar'
			'sidebar main nav';
		grid-template-columns: auto 1fr auto;
		grid-template-rows: auto 1fr;
	}

	main {
		grid-area: main;
		position: relative;
	}

	.topbar,
	.sidebar {
		display: flex;
		justify-content: center;
		margin: 0;
		padding: 1rem;
	}

	.topbar {
		grid-area: topbar;
		border-bottom: 1px solid var(--color-separator);
	}

	.sidebar {
		grid-area: sidebar;
		border-right: 1px solid var(--color-separator);
	}
</style>

<script>
	import SignInIcon from '$lib/images/sign-in.svelte';
	import SunMoonIcon from '$lib/images/sun-moon.svelte';
	import FontSizeIcon from '$lib/images/font-size.svelte';
	import FullScreenIcon from '$lib/images/full-screen.svelte';
	import PracticeIcon from '$lib/images/practice.svelte';
	import ProfileIcon from '$lib/images/profile.svelte';
	import TypingTestIcon from '$lib/images/typing-test.svelte';
	import HelpIcon from '$lib/images/help.svelte';
	import HighScoresIcon from '$lib/images/high-scores.svelte';
	import MultiplayerIcon from '$lib/images/multiplayer.svelte';
	import LayoutsIcon from '$lib/images/layouts.svelte';
	import TextToolsIcon from '$lib/images/text-tools.svelte';
</script>

<nav>
	<div class="nav-items">
		<div class="nav-item sign-in">
			<a href="/" title="Sign‑in for an online account.">
				<SignInIcon />
				<span>Sign-In</span>
			</a>
		</div>

		<div class="nav-item options">
			<button><SunMoonIcon /></button>
			<button><FontSizeIcon /></button>
			<button><FullScreenIcon /></button>
		</div>

		<div class="nav-item">
			<a href="/" title="Practice typing lessons to improve your typing speed.">
				<PracticeIcon />
				<span>Practice</span></a
			>
		</div>

		<div class="nav-item">
			<a href="/" title="See the detailed statistics about your learning progress."
				><ProfileIcon /><span>Profile</span></a
			>
		</div>

		<div class="nav-item">
			<a href="/" title="Take a typing speed test."><TypingTestIcon /><span>Typing Test</span></a>
		</div>

		<div class="nav-item">
			<a href="/" title="Get the instructions on how to use this application."
				><HelpIcon /><span>Help</span></a
			>
		</div>

		<div class="nav-item">
			<a href="/" title="See the high score table featuring the fastest typists."
				><HighScoresIcon /><span>High Scores</span></a
			>
		</div>

		<div class="nav-item">
			<a href="/" title="Compete against other players in an online multiplayer game."
				><MultiplayerIcon /><span>Multiplayer</span></a
			>
		</div>

		<div class="nav-item">
			<a href="/" title="Compare the efficiency of different keyboard layouts."
				><LayoutsIcon /><span>Layouts</span></a
			>
		</div>

		<div class="nav-item">
			<a href="/" title="Count the characters and words in your text."
				><TextToolsIcon /><span>Text Tools</span></a
			>
		</div>

		<div class="nav-item">
			<div class="socials">
				<a
					href="mailto:info@keybr.com"
					target="email"
					title="Send your comments and suggestions to info@keybr.com">info@keybr.com</a
				><a
					href="https://discord.gg/gY4RA4enVH"
					target="discord"
					title="Discuss on our Discord server.">Discord</a
				><a
					href="https://groups.google.com/g/keybr"
					target="groups"
					title="Discuss on Google Groups.">Google Groups</a
				><a href="/" title="Terms of service.">Terms of Service</a><a
					href="/"
					title="Privacy policy.">Privacy Policy</a
				><span
					><a href="/" title="German (Deutsch)">de</a>
					<a href="/" title="English">en</a>
					<a href="/" title="Spanish (Español)">es</a>
					<a href="/" title="French (Français)">fr</a>
					<a href="/" title="Polish (Polski)">pl</a>
					<a href="/" title="Russian (Русский)">ru</a></span
				>
			</div>
		</div>
	</div>
</nav>

<style>
	nav {
		grid-area: nav;
		margin: 0;
		padding: 1rem;
		color: var(--color-text);
		border-left: 1px solid var(--color-separator);
	}

	.nav-items {
		margin: 0;
		max-width: 12rem;
		padding: 0;
		position: sticky;
		top: 0;
	}

	.nav-item {
		border-bottom: 1px solid var(--color-separator);
	}

	.nav-item a {
		color: var(--color-nav-link);
		text-decoration: none;
	}

	.nav-item > a {
		display: flex;
		align-items: center;
		height: 3rem;
		justify-content: left;
		line-height: 3rem;
		margin: 0;
		padding: 0 1rem;
	}

	.nav-item a:hover {
		background-color: var(--color-nav-link--current);
	}

	.nav-item a span {
		margin-left: 0.5rem;
		max-width: 100%;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}

	.sign-in a {
		height: unset;
		align-items: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 1rem 0;
	}

	.sign-in a :global(svg) {
		height: 4rem;
		width: 4rem;
	}

	.sign-in a span {
		max-width: 10rem;
		text-align: center;
		white-space: normal;
		margin: 0;
		line-height: 1.5rem;
	}

	.options {
		align-items: center;
		display: flex;
		height: 3rem;
		justify-content: center;
	}

	.socials {
		display: flex;
		align-items: center;
		flex-direction: column;
		font-size: 0.8rem;
		justify-content: center;
		margin: 0;
		padding: 1rem 0;
		text-align: center;
	}

	.socials a:hover {
		text-decoration: underline dotted var(--color-text);
		background-color: unset;
	}
</style>

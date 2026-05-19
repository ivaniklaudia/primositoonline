<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="shell">
	{@render children()}
</div>

<style>
	:global(*),
	:global(*::before),
	:global(*::after) {
		box-sizing: border-box;
	}

	:global(body) {
		margin: 0;
		min-height: 100vh;
		background: #0f0e0d;
		color: #e8e4df;
		font-family:
			system-ui,
			'Segoe UI',
			Roboto,
			'Helvetica Neue',
			Arial,
			sans-serif;
		line-height: 1.5;
		-webkit-font-smoothing: antialiased;
	}

	:global(a) {
		color: #c9a962;
		text-decoration-thickness: 1px;
		text-underline-offset: 0.2em;
	}

	:global(a:hover) {
		color: #e4d4a8;
	}

	.shell {
		min-height: 100vh;
	}
</style>

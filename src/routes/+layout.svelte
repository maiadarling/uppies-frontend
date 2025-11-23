<script lang="ts">
	import favicon from '$lib/assets/favicon.svg'
	import '../css/app.scss'

	import Sidebar from '../components/sidebar.svelte'

	let { children } = $props()
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="app flex row gap-xl">
	<Sidebar />

	<main>
		{@render children()}
	</main>
</div>
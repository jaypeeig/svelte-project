
<script context="module">
	export function load({ error, status }) {
		return {
			props: { error, status },
		}
	}
</script>

<script>
	export let status
	export let error
	const offline = typeof navigator !== 'undefined' && navigator.onLine === false
	const title = offline ? 'Offline' : status
	const message = offline ? 'Find the internet and try again' : error.message
</script>

<svelte:head>
	<title>Coding: {title}</title>
</svelte:head>

<section>
	<h1>Error <sup>{title}</sup></h1>
  <a href="/">Back to hom<sup>e</sup>page</a>
	<code>
		{message}
	</code>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	a {
		margin: 10px;
	}
	section a:hover{
		text-decoration: none;
		text-shadow: 1px 1px var(--primary-color);
	}


</style>
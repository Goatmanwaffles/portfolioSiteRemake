<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import "../app.css";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<style>
@font-face {
  font-family: satoshi;
  font-style: normal;
  font-weight: 200 700;
  font-display: swap;
  src: url('$lib/assets/css/satoshi.css') format("woff2");
}

</style>

{@render children()}

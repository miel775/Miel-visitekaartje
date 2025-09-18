<script>
	import favicon from '$lib/assets/favicon.svg';
	let { children } = $props();
</script>

<svelte:head>
  <link href="https://fonts.cdnfonts.com/css/garet" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Jersey+20&display=swap" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" rel="stylesheet">
</svelte:head>

{@render children?.()}


<script lang="ts">
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { Modal } from '@skeletonlabs/skeleton';
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="true" />
	<link
		href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;700&family=Roboto:wght@400;700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>
<div class="flex h-full max-h-screen w-full items-center justify-center overflow-y-auto">
	<Modal />
	<slot />
</div>

<script lang="ts">
	import { page } from '$app/stores';
	$: currentPage = $page.url.pathname;

	const links = [
		{
			name: 'Products',
			path: '/admin/products'
		},
		{
			name: 'Orders',
			path: '/admin/orders'
		},
		{
			name: 'Customers',
			path: '/admin/customers'
		},
		{
			name: 'Statistics',
			path: '/admin/statistics'
		},
		{
			name: 'Reviews',
			path: '/admin/reviews'
		},
		{
			name: 'Hot offers',
			path: '/admin/hot-offers'
		},
		{
			name: 'Settings',
			path: '/admin/settings'
		}
	];
	let haveNotifications = true;
</script>

<svelte:head>
	<script src="https://code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js"></script>

	<title>Ecommerce | Admin</title>
</svelte:head>
<div class="flex h-full max-h-screen w-full justify-center overflow-y-hidden">
	<div class="flex w-full max-w-7xl justify-center">
		<aside class="h-full w-64">
			<a href="/admin" class="flex h-20 items-center justify-center text-2xl">Ecommerce</a>
			<ul class="flex flex-col p-3">
				{#each links as link}
					{#if currentPage.includes(link.path)}
						<li
							class={`flex rounded-md bg-slate-500 p-3 hover:bg-black hover:bg-opacity-10
							`}
						>
							<a href={link.path}>{link.name}</a>
						</li>
					{:else}
						<li class={`flex rounded-md hover:bg-black hover:bg-opacity-10`}>
							<a href={link.path} class="w-full p-3">{link.name}</a>
						</li>
					{/if}
				{/each}
			</ul>
		</aside>
		<main class="h-full w-full">
			<header class="flex h-20 w-full items-center justify-between p-6">
				<span>Search</span>
				<span class="flex items-center gap-4">
					<button
						class={`relative flex items-center justify-center ${
							haveNotifications
								? 'before:absolute before:right-1 before:top-1 before:h-2 before:w-2 before:rounded-full before:bg-red-500'
								: ''
						}`}
					>
						<iconify-icon icon="mdi:bell" style="color: #bbb;" width="28" />
					</button>
					<button class="flex items-center">
						<span
							class="flex h-10 w-10 items-center justify-center rounded-full bg-green-600 text-xl"
							>JS</span
						>
						<iconify-icon
							icon="iconamoon:arrow-up-2"
							style="color: #bbb;"
							rotate="180deg"
							width="28"
						/>
					</button>
				</span>
			</header>
			<div class="h-full p-4">
				<slot />
			</div>
		</main>
	</div>
</div>

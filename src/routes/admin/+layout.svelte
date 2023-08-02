<script lang="ts">
	const links = [
		{
			name: 'Dashboard',
			path: '/admin'
		},
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
			name: 'Transactions',
			path: '/admin/transactions'
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
<div class="flex h-full w-full justify-center">
	<div class="flex w-full max-w-7xl">
		<aside class="h-full w-64">
			<div class="flex h-20 items-center justify-center text-2xl">Ecommerce</div>
			<ul class="flex flex-col p-3">
				{#each links as link}
					<li class={`flex rounded-md p-3 hover:bg-black hover:bg-opacity-10`}>
						<a href={link.path}>{link.name}</a>
					</li>
				{/each}
			</ul>
		</aside>
		<main class="h-full flex-1">
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
			<div class="p-4">
				<slot />
			</div>
		</main>
	</div>
</div>

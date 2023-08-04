<script lang="ts">
	import { Table, tableMapperValues } from '@skeletonlabs/skeleton';
	import type { ModalComponent, TableSource } from '@skeletonlabs/skeleton';

	// Provide the modal settings

	// Trigger the modal:
	// modalStore.trigger(modal);

	const orders = [
		{
			id: 2323,
			customer: 'John Doe',
			email: 'johndoe@example.com',
			value: '$ 100.00',
			status: 'Delivered',
			date: '09-01-2022'
		},
		{
			id: 2323,
			customer: 'John Doe',
			email: 'johndoe@example.com',
			value: '$ 100.00',
			status: 'Cancelled',
			date: '09-01-2022'
		},
		{
			id: 2323,
			customer: 'John Doe',
			email: 'johndoe@example.com',
			value: '$ 100.00',
			status: 'Pending',
			date: '09-01-2022'
		},
		{
			id: 2323,
			customer: 'John Doe',
			email: 'johndoe@example.com',
			value: '$ 100.00',
			status: 'Delivered',
			date: '09-01-2022'
		},
		{
			id: 2323,
			customer: 'John Doe',
			email: 'johndoe@example.com',
			value: '$ 100.00',
			status: 'Delivered',
			date: '09-01-2022'
		}
	];
</script>

<svelte:head>
	<script src="https://code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js"></script>

	<title>Ecommerce | Admin Orders</title>
</svelte:head>
<div class=" flex h-full flex-col gap-3">
	<h1 class="text-2xl">Orders</h1>
	<section class=" rounded-md">
		<div class="grid gap-2">
			{#each orders as order}
				<a
					href={`/admin/orders/${order.id}`}
					class="flex items-center justify-between rounded-md bg-secondary-500 p-2 text-sm"
				>
					<span class="">{order.id}</span>
					<span class="w-[30%] text-left font-bold">{order.customer}</span>
					<span class="text-left">{order.email}</span>
					<span>{order.value}</span>
					<span class="flex justify-center py-4">
						<span
							class={`rounded-2xl p-2 font-bold ${
								order.status === 'Delivered'
									? 'bg-green-300 text-green-700'
									: order.status === 'Cancelled'
									? 'bg-red-400 text-red-700'
									: 'bg-yellow-400 text-yellow-700'
							}`}>{order.status}</span
						>
					</span>
					<span>{order.date}</span>
				</a>
			{/each}
		</div>
	</section>
</div>

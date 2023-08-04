<script lang="ts">
	import { Table, tableMapperValues } from '@skeletonlabs/skeleton';
	import type { ModalComponent, TableSource } from '@skeletonlabs/skeleton';
	import { modalStore, type ModalSettings } from '@skeletonlabs/skeleton';
	import CreateProducts from './components/CreateProducts.svelte';

	const modalComponent: ModalComponent = {
		// Pass a reference to your custom component
		ref: CreateProducts,
		// Add the component properties as key/value pairs
		props: { background: 'bg-red-500' }
		// Provide a template literal for the default component slot
	};
	// Provide the modal settings
	const modal: ModalSettings = {
		type: 'component',
		component: modalComponent
	};

	// Trigger the modal:
	// modalStore.trigger(modal);

	const productsData = [
		{
			id: 1,
			img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
			name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
			price: '$64.92',
			soldLast30Days: 10
		},
		{
			id: 2,
			img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
			name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
			price: '$64.92',
			soldLast30Days: 10
		},
		{
			id: 3,
			img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
			name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
			price: '$64.92',
			soldLast30Days: 10
		},
		{
			id: 4,
			img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
			name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
			price: '$64.92',
			soldLast30Days: 10
		}
	];
</script>

<svelte:head>
	<script src="https://code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js"></script>

	<title>Ecommerce | Admin Products</title>
</svelte:head>
<div class=" flex h-full flex-col gap-3">
	<header class="flex items-center justify-between">
		<h1 class="text-2xl">Products</h1>
		<button class="btn bg-primary-500" on:click={() => modalStore.trigger(modal)}>Add</button>
	</header>
	<section class=" rounded-md bg-secondary-500 p-3">
		<table class="w-full border-collapse text-sm">
			<thead>
				<tr class="text-center">
					<th class="" />
					<th class="py-2 text-center">Name</th>
					<th class="text-center">Price</th>
					<th class="text-center">Sold last 30 days</th>
					<th>Actions</th>
				</tr>
			</thead>
			<tbody>
				{#each productsData as product}
					<tr class="py-2">
						<td class="w-[15%] py-2">
							<img src={product.img} alt={product.name} class="h-16 w-16 rounded-md object-cover" />
						</td>
						<td class="w-[40%] text-left"
							>{product.name.length > 40 ? product.name.slice(0, 40) + '...' : product.name}</td
						>
						<td class="py-2 text-center">{product.price}</td>
						<td class="text-center">{product.soldLast30Days}</td>
						<td class="text-center">
							<button class="btn-icon btn-icon-sm bg-primary-500"
								><iconify-icon icon="mdi:pencil" style="color: #fff;" /></button
							>
							<button class="btn-icon btn-icon-sm bg-primary-500"
								><iconify-icon icon="mdi:delete" style="color: #fff;" /></button
							>
						</td>
					</tr>
				{/each}
			</tbody>
		</table>
	</section>
</div>

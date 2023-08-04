<script lang="ts">
	import { page } from '$app/stores';
	let orderId = $page.params.id;
	let order = {
		customer: {
			name: 'John Doe',
			email: 'johndoe@example.com'
		},
		date: '09-01-2022 12:14',
		status: 'Delivered',
		products: [
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			},
			{
				id: 1,
				img: 'https://http2.mlstatic.com/D_NQ_NP_666941-MLB53122641325_012023-O.webp',
				name: 'Camisa Social Masculina Slim Fit Luxo Pronta Entrega',
				price: '$64.92',
				quantity: 2
			}
		]
	};
</script>

<div class=" relative flex h-full flex-col gap-3">
	<header class="flex items-center justify-between">
		<h1 class="text-2xl">Order #{orderId}</h1>
		<a
			href={`/admin/orders/${orderId}/message`}
			class="h-15 w-15 flex items-center justify-center rounded-full bg-green-600 p-2"
		>
			<iconify-icon icon="mdi:chat" style="color: white;" width="48" />
		</a>
	</header>

	<div class="grid">
		<div class="grid grid-cols-2 gap-2">
			<div class="grid">
				<span>Customer's name</span>
				<span>{order.customer.name}</span>
			</div>
			<div class="grid">
				<span>Customer's Email</span>
				<span>{order.customer.email}</span>
			</div>
			<div class="grid">
				<span>Date</span>
				<span>{order.customer.email}</span>
			</div>
			<div class="grid">
				<span>Status</span>
				<span>{order.status}</span>
			</div>
		</div>
	</div>
	<section class=" rounded-md bg-secondary-500 p-3">
		<table class="block h-full w-full border-collapse text-sm">
			<thead class="block w-full">
				<tr class="grid w-full grid-cols-12 text-center">
					<th class="col-span-2" />
					<th class="col-span-6 flex items-center py-2">Name</th>
					<th class="col-span-2 flex items-center justify-center">Price</th>
					<th class="col-span-2 flex items-center justify-center">Quantity</th>
				</tr>
			</thead>
			<tbody class="block h-96 max-h-96 w-full overflow-y-auto">
				{#each order.products as product}
					<tr class="grid grid-cols-12 py-2">
						<td class="col-span-2 flex justify-center py-2">
							<img
								src={product.img}
								alt={product.name}
								class="aspect-square w-[60%] rounded-md object-cover"
							/>
						</td>
						<td class="col-span-6 flex items-center pl-3"
							>{product.name.length > 40 ? product.name.slice(0, 40) + '...' : product.name}</td
						>
						<td class="col-span-2 flex items-center justify-center py-2">{product.price}</td>
						<td class="col-span-2 flex items-center justify-center">{product.quantity}</td>
					</tr>
				{/each}
			</tbody>
		</table>
	</section>
</div>

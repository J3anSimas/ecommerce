<script lang="ts">
	import { Chart, Colors } from 'chart.js/auto';
	import ChartDataLabels from 'chartjs-plugin-datalabels';

	import { onMount } from 'svelte';
	let sales = [20, 10, 5, 2, 20, 30, 45];
	let months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
	let productSalesValues = [20, 10, 5, 2, 20];
	let productSalesLabels = ['Shoes', 'T-Shirt', 'Pants', 'Socks', 'Jacket'];
	let salesStatisticChart: HTMLCanvasElement;
	let productSalesChart: HTMLCanvasElement;

	onMount(async () => {
		Chart.register(Colors);
		Chart.register(ChartDataLabels);
		new Chart(salesStatisticChart, {
			type: 'bar',
			data: {
				xLabels: months,
				datasets: [
					{
						label: 'Sales',
						data: sales,
						borderColor: '#fff',
						backgroundColor: 'rgb(15, 186, 129)',
						borderRadius: 15,
						borderSkipped: false,
						datalabels: {
							color: '#fff',
							anchor: 'end',
							align: 'bottom'
						}
					}
				]
			},

			options: {
				color: '#fff',
				scales: {
					x: {
						border: {
							display: false
						},
						grid: {
							display: false
						},
						type: 'category',
						ticks: {
							color: '#fff'
						}
					},
					y: {
						border: {
							display: false
						},
						grid: {
							display: false
						},
						ticks: {
							color: '#fff'
						}
					}
				},
				plugins: {
					legend: {
						display: false,
						labels: {
							color: '#fff'
						}
					}
				}
			}
		});
		new Chart(productSalesChart, {
			type: 'doughnut',
			data: {
				labels: productSalesLabels,
				datasets: [
					{
						label: 'Top 5 Products',
						data: productSalesValues,
						borderColor: '#fff',
						backgroundColor: [
							'rgb(248 113 113)',
							'rgb(96 165 250)',
							'rgb(74 222 128)',
							'rgb(250 204 21)',
							'rgb(251 146 60)'
						],
						borderWidth: 0,
						datalabels: {
							color: '#fff'
						}
					}
				]
			},
			plugins: [ChartDataLabels],
			options: {
				plugins: {
					legend: {
						display: true,

						labels: {
							color: '#fff',
							pointStyle: 'circle'
						},
						position: 'bottom'
					},
					colors: {
						enabled: true
					}
				}
			}
		});
	});

	const cards = [
		{
			icon: 'mdi:currency-usd',
			title: 'Total Sales',
			value: '$ 1,250,342,221.00',
			color: 'bg-yellow-500'
		},
		{
			icon: 'mdi:cart',
			title: 'Total Orders',
			value: '1,250',
			color: 'bg-green-500'
		},
		{
			icon: 'mdi:basket',
			title: 'Total Products',
			value: '250',
			color: 'bg-blue-500'
		}
	];

	const latestOrders = [
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

<div class="flex flex-col gap-3">
	<h1 class="text-2xl">Dashboard</h1>

	<section class="">
		<ul class="grid grid-cols-3 gap-2">
			{#each cards as card}
				<li class="flex items-center gap-3 rounded-md bg-secondary-500 p-3">
					<span class={`flex items-center justify-center rounded-full ${card.color} p-2`}>
						<iconify-icon icon={card.icon} style="color: #fff;" width="24" />
					</span>
					<span class="flex flex-col">
						<span class="text-sm font-light text-slate-200">{card.title}</span>
						<span class="text-lg font-bold">{card.value}</span>
					</span>
				</li>
			{/each}
		</ul>
	</section>
	<section class="grid grid-cols-3 gap-2">
		<div class="col-span-2 flex flex-col gap-3 rounded-md bg-secondary-500 p-3">
			<p>Sales Statistics</p>
			<canvas bind:this={salesStatisticChart} />
		</div>
		<div class="flex flex-col gap-3 rounded-md bg-secondary-500 p-3">
			<p>Products Sales</p>
			<canvas bind:this={productSalesChart} />
		</div>
	</section>
	<section class="rounded-md bg-secondary-500 p-3">
		<h1 class="text-xl">Latest Orders</h1>
		<div class="flex flex-col gap-3 rounded-md bg-secondary-500 p-3">
			<table class="w-full">
				<tbody>
					{#each latestOrders as order}
						<tr class="text-sm">
							<td class="">{order.id}</td>
							<td class="w-[30%] text-left font-bold">{order.customer}</td>
							<td class="text-left">{order.email}</td>
							<td>{order.value}</td>
							<td class="flex justify-center py-4">
								<span
									class={`rounded-2xl p-2 font-bold ${
										order.status === 'Delivered'
											? 'bg-green-300 text-green-700'
											: order.status === 'Cancelled'
											? 'bg-red-400 text-red-700'
											: 'bg-yellow-400 text-yellow-700'
									}`}>{order.status}</span
								>
							</td>
							<td>{order.date}</td>
							<td class="text-right"
								><button>
									<iconify-icon icon="mdi:dots-horizontal" />
								</button></td
							>
						</tr>
					{/each}
				</tbody>
			</table>
		</div>
	</section>
</div>

<script lang="ts">
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
</script>

<div class="flex flex-col gap-3">
	<h1 class="text-2xl">Dashboard</h1>

	<section class="">
		<ul class="grid grid-cols-3">
			{#each cards as card}
				<li class="flex items-center gap-3 p-3">
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
</div>

<script lang="ts">
	import { page } from '$app/stores';
	let orderId = $page.params.id;
	let messages = [
		{
			id: 1,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:12',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message:
				'LLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumLorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatumorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		},
		{
			id: 2,
			message: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.',
			date: '09-01-2022 12:14',
			from: 'John Doe'
		}
	];
</script>

<div class="flex h-full flex-col gap-2">
	<h1 class="text-2xl">Messages</h1>
	<div class="grid max-h-[80%] gap-2 overflow-scroll rounded-md py-2 pr-2">
		{#each messages as message}
			<div class="flex flex-col gap-2 rounded-md bg-secondary-500 p-2">
				<span>{message.from}</span>
				<span>{message.message}</span>
				<span class="flex justify-end text-xs">{message.date}</span>
			</div>
		{/each}
	</div>
	<div>
		<form class="flex gap-2">
			<input
				type="text"
				class="flex-1 rounded-md border-none bg-secondary-500 p-3"
				placeholder="Type your message here"
			/>
			<button class="rounded-md bg-secondary-500 p-2">Send</button>
		</form>
	</div>
</div>

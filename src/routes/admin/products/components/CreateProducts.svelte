<script lang="ts">
	export const parent = '';
	export const background = '';
	const categories = ['Casual', 'Formal', 'Sport', 'Elegant'];
	let imagesToUpload = [] as File[];
	let tempImages: FileList | undefined;
	$: if (tempImages) {
		imagesToUpload.push(...tempImages);
		imagesToUpload = imagesToUpload;
		tempImages = undefined;
	}
	let imageInput: HTMLInputElement;
	let mockImages = [1, 1, 1, 1, 1, 1];
</script>

<form action="" class="grid w-96 gap-2 rounded-md bg-secondary-500 p-3">
	<div class="grid gap-2">
		<label for="name" class="label">Name</label>
		<input type="text" class="input rounded-md" name="name" placeholder="Name of the product" />
	</div>
	<div class="grid gap-2">
		<label for="description">Description</label>
		<textarea class="textarea" name="description" rows="3" />
	</div>
	<div class="form-group">
		<label for="price">Price</label>
		<input type="number" class="input rounded-md" name="price" placeholder="Price of the product" />
	</div>
	<div class="h-auto rounded-md">
		<label for="stock">Categories</label>
		<div class="grid grid-cols-3">
			{#each categories as category}
				<span class="flex items-center gap-1"
					><input type="checkbox" class="form-control" name="categories" value={category} />
					{category}
				</span>
			{/each}
		</div>
	</div>
	<div class="form-group">
		<label for="image">Images</label>
		<input
			type="file"
			accept="image/*"
			bind:files={tempImages}
			bind:this={imageInput}
			class="form-control-file hidden"
			multiple
		/>

		{#if imagesToUpload.length > 0}
			<div
				class="flex h-20 w-full max-w-[360px] flex-nowrap gap-2 overflow-x-scroll whitespace-nowrap"
			>
				<div
					class="flex h-full min-w-[5rem] items-center justify-center rounded-md border border-dashed"
				>
					<button
						class={`h-full  w-full `}
						type="button"
						on:click={() => imageInput.click()}
						on:keydown={(e) => {
							if (e.key === 'Enter') {
								imageInput.click();
							}
						}}
					>
						<iconify-icon icon="mdi:camera" style="color: #bbb;" />
					</button>
				</div>
				{#each imagesToUpload as image}
					<div class="group relative flex h-full min-w-[5rem]">
						<button
							type="button"
							on:click={() => {
								imagesToUpload = imagesToUpload.filter((img) => img !== image);
							}}
							class="absolute hidden h-full w-full items-center justify-center rounded-md bg-black bg-opacity-60 group-hover:flex"
						>
							<span class="flex h-8 w-8 items-center justify-center rounded-full bg-blue-500">
								<iconify-icon icon="mdi:delete" style="color: #fff;" />
							</span>
						</button>
						<img
							src={URL.createObjectURL(image)}
							alt=""
							class="h-full w-20 rounded-md object-cover"
						/>
					</div>
				{/each}
			</div>
		{:else}
			<div class="h-20 w-full">
				<div class="flex h-full w-full items-center justify-center rounded-md border border-dashed">
					<button
						class={`h-full  w-full `}
						type="button"
						on:click={() => imageInput.click()}
						on:keydown={(e) => {
							if (e.key === 'Enter') {
								imageInput.click();
							}
						}}
					>
						<iconify-icon icon="mdi:camera" style="color: #bbb;" />
					</button>
				</div>
			</div>
		{/if}
	</div>
	<button type="button" class="btn-lg variant-outline-primary rounded-md font-bold">Create</button>
</form>
<slot />

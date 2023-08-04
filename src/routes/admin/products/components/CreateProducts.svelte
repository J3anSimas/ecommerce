<script lang="ts">
	export const parent = '';
	export const background = '';
	const categories = ['Casual', 'Formal', 'Sport', 'Elegant'];
	let imagesToUpload = [] as File[];
	let tempImages: FileList;
	$: if (tempImages) {
		imagesToUpload.push(...tempImages);
		imagesToUpload = imagesToUpload;
	}
	let imageInput: HTMLInputElement;
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
		<div class="h-20 w-full">
			<div class="flex h-full w-full items-center justify-center rounded-md border border-dashed">
				<button
					class={`h-full ${imagesToUpload.length > 0 ? 'w-20' : 'w-full'} `}
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
				{console.log(image)}
				<img src={URL.createObjectURL(image)} alt="" class="h-full w-20" />
			{/each}
		</div>
	</div>
	<button type="button" class="btn-lg variant-outline-primary rounded-md font-bold">Create</button>
</form>
<slot />

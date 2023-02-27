<script lang="ts">
	import { open } from '@tauri-apps/api/dialog';
	import { readTextFile, BaseDirectory } from '@tauri-apps/api/fs';

	let contents = [''];

	const readFileContents = async () => {
		try {
			const selectedPath = await open({
				multiple: true,
				// directory: true,
				title: 'Open Text File',
				filters: [
					{
						name: 'Image',
						extensions: ['png', 'jpeg', 'webp', 'svg', 'cbz', 'cbr', 'pdf']
					}
				]
			});
			// contents.value = await readTextFile(selectedPath as string);
			console.log(selectedPath);
		} catch (err) {
			console.error(err);
		}
	};
</script>

<body class="h-screen w-screen bg-gradient-to-b from-[#141414] to-[#000000]">
	<h1 class="flex font-semibold justify-center">Welcome to Comics</h1>
	<div class="flex justify-center p-10">
		{#if Array.isArray(contents)}<p>{{ contents }}</p>
			<button
				class="object-contain rounded bg-[#97181c] hover:bg-[#d81f26] p-1"
				on:click={readFileContents}>Open File Explorer</button
			>
		{/if}
	</div>
</body>

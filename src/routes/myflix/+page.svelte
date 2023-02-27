<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=539cfa79a36ad21a831649e067138ebe&language=en-US&page=1`
		);
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	export let popular;
	console.log(popular);
</script>
<body class="h-screen w-screen bg-gradient-to-b from-[#141414] to-[#000000]">
	<h1 class="flex font-semibold justify-center">Welcome to MyFlix</h1>
	<div class="flex justify-center p-10">
		<button class="object-contain rounded bg-[#97181c] hover:bg-[#d81f26] p-1">Open File Explorer</button>
	</div>
</body>

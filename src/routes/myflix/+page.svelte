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

<h1>Hello</h1>


<style lang="postcss">
	:global(html) {
		background-color: #3f3f3f;
	}
</style>

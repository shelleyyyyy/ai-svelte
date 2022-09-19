<script>
	import Row from "$lib/main/Row.svelte";

	const grid = {
		"size": "8*8",
		"agents": 3,
		"rows": [
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"a",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
		]
	}

</script>

<div class="flex">
	<span class="flex flex-wrap justify-center shadow-xl rounded-md gap-5 bg-white p-5">
		{#each grid.rows as row}
			<Row arr={row}></Row>
		{/each}
	</span>
</div>
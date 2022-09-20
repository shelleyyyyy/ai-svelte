<script>
	import Row from "$lib/main/Row.svelte";
	import Grid from "$lib/main/Grid.svelte";

	const random = () => {
		return Math.floor(Math.random() * 4);
	}
	let block = []
	for(let i = 0; i < 7; i++){
		let arr = []
		for(let i = 0; i < 7; i++){
			let ran = random()
			if(ran == 1){
				arr.push("o")
			} else if(ran == 2){
				arr.push("c")
			} else if(ran == 3){
				arr.push("a")
			} else{
				arr.push("c")
			}
		}
		block.push(arr)
	}
	random
	const grid = {
		"rows": [
			[
				"c",
				"c",
				"c",
				"c",
				"c",
				"c",
				"c"
			],
			[
				"o",
				"c",
				"o",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"o",
				"p-r",
				"a",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"o",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"o",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"o",
				"p-u",
				"p-r",
				"p-d",
				"p-l"
			],
			[
				"o",
				"c",
				"o",
				"a",
				"p-r",
				"p-d",
				"p-l"
			],
		]
	}

	let size = grid.size

	grid.rows = block

</script>

<div class="flex justify-center">
	<Grid rows={grid.rows} size={grid.size}></Grid>
</div>
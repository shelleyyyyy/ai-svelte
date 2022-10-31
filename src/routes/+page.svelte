<script>
import Row from "$lib/main/Row.svelte";
import Grid from "$lib/main/Grid.svelte";
import { GridSharp } from "svelte-ionicons";

	// const random = () => {
	// 	return Math.floor(Math.random() * 4);
	// }
	// let block = []
	// for(let i = 0; i < 30; i++){
	// 	let arr = []
	// 	for(let i = 0; i < 30; i++){
	// 		let ran = random()
	// 		if(ran == 1){
	// 			arr.push("o")
	// 		} else if(ran == 2){
	// 			arr.push("c")
	// 		} else if(ran == 3){
	// 			arr.push("a")
	// 		} else{
	// 			arr.push("c")
	// 		}
	// 	}
	// 	block.push(arr)
	// }
	// random
	const stuff = {
		grids: [
			{
				"rows": [
					[
						"a",
						"c",
						"c",
						"c",
						"c",
						"p-u",
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
				],
			},
			{
				"rows": [
					[
						"c",
						"a",
						"c",
						"c",
						"c",
						"p-u",
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
				],
			},
			{
				"rows": [
					[
						"a",
						"a",
						"a",
						"a",
						"a",
						"a-u",
						"a"
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
				],
			}
			
		],
		"size": 10
	}

	// let size = grid.size

	// grid.rows = block

	
	let rows = stuff.grids[0].rows
	async function pleaseWork(){
		rows = stuff.grids[0].rows
		for(let i = 0; i < stuff.grids.length; i++){
		rows = stuff.grids[i].rows
		// sleep for one second
		await new Promise(r => setTimeout(r, 1000));

		// log stuff
		console.log(rows)
		}
	}
	

	function run(){
		pleaseWork()
	}
</script>

<div>
	<div class="flex justify-center">
		<!-- run button -->
		<button  class="px-20 py-10 my-5 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded" on:click={run}>Run</button>
	</div>
	<div>
		<Grid rows={rows} size={stuff.size}></Grid>
	</div>
</div>
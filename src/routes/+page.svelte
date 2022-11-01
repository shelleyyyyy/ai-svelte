<script>

	import Grid from "$lib/main/Grid.svelte";
	
	const data = {
			grid: [
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
					"o",
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
					"g",
					"p-r",
					"p-d",
					"p-l"
				],
				[
					"o",
					"c",
					"o",
					"g",
					"p-r",
					"p-d",
					"p-l"
				],
				[
					"o",
					"c",
					"o",
					"g",
					"p-r",
					"p-d",
					"p-l"
				],
				[
					"o",
					"c",
					"o",
					"g",
					"p-r",
					"p-d",
					"p-l"
				],
				[
					"o",
					"c",
					"o",
					"g",
					"p-r",
					"p-d",
					"p-l"
				],
				[
					"o",
					"c",
					"o",
					"g",
					"p-r",
					"p-d",
					"p-l"
				],
			],
			sequince: [
				"l",
				"r",
				"r",
				"m",
				"m",
				"m",
				"m",
				'l',
				'm',
				'm',
				'm',
				'r',
				'm',
				'm',
			],
			x: 0,
			y: 0,
			dir: 1,
			size: 50,
	}

	let sequince = data.sequince;

	$: local_grid = data.grid;

	let x = data.x;
	let y = data.y;

	let dir = data.dir;

	let size = 10

	
	function reset(){

		sequince = data.sequince;

		local_grid = data.grid;

		x = data.x;

		y = data.y;

		dir = data.dir;

		size = 10
	}

	function move(){
		switch(dir){
			case 0:
				// move up
				console.log("up")
				local_grid[x][y] = "p-u"
				x -= 1
				break;
			case 1:
				// move right
				console.log("right")
				local_grid[x][y] = "p-r"
				y += 1
				break;
			case 2:
				// move down
				console.log("down")
				local_grid[x][y] = "p-d"
				x += 1
				break;
			case 3:
				// move left
				console.log("left")
				local_grid[x][y] = "p-l"
				y -= 1
				break;
		}
		local_grid[x][y] = "a"
		
	}

	async function run(){
		for(let i = 0; i < sequince.length; i++){

			await new Promise(r => setTimeout(r, 500));
			// sleep for 1 second

			switch (sequince[i]){
				case "l":
					// move left
					console.log("left")
					dir = (dir + 3) % 4
					console.log(dir)
					break;
				case "r":
					// move right
					console.log("right")
					dir = (dir + 1) % 4
					console.log(dir)
					break;
				case "m":
					// move forward
					move()
					break;
					
			}
		}
	}

	function pleaseWork(){
		run();
	}

	let name = data.size;
</script>

<h1 class="text-center text-6xl my-10">TRICK AGENT WORLD</h1>

<div class="flex justify-center">
	<div class="w-96 border-1 border-black">
		<div class="p-5 grid grid-cols-2 h-40 gap-3 ">
			<div class="flex justify-center">
				<button  class="w-36 py-5 my-5 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded" on:click={pleaseWork}>Run</button>
			</div>
			<div class="flex justify-center">
				<button  class="w-36 py-5 my-5 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded" on:click={reset}>Reset</button>
			</div>
		</div>
		<div>
			<!-- input grid size text input -->
			<div class="grid justify-center">
				<!-- label -->
				<h1 for="gridSize" class="text-2xl text-center">Grid Size</h1>
				<input type="text" class="w-36 py-5 my-5 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded" bind:value={size}>
			</div>
		</div>
	</div>
	<div>
		<Grid dir={dir} rows={local_grid} size={size}></Grid>
	</div>
</div>

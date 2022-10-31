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
				'm',
				'm',
			],
			x: 0,
			y: 0,
			dir: 1,
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
					break;
			}
		}
	}

	function pleaseWork(){
		run();
	}

	let name = 10;
</script>

<h1 class="text-center text-6xl my-10">TRICK AGENT WORLD</h1>

<div class="flex justify-center">
	<div class="w-96">
		<div class="p-5 grid grid-cols-2 h-40 gap-3">
			<div class="flex justify-center">
				<button  class="w-36 py-5 my-5 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded" on:click={pleaseWork}>Run</button>
			</div>
			<div class="flex justify-center">
				<button  class="w-36 py-5 my-5 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded" on:click={reset}>Reset</button>
			</div>
		</div>
		<div>
			<h1>input grid size </h1>
			<input bind:value={name}>
		</div>
	</div>
	<div>
		<Grid dir={dir} rows={local_grid} size={size}></Grid>
	</div>
</div>

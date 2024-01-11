<script lang="ts">
	import AlmostHexagon from './almost-hexagon.svelte';
	import Square from './square.svelte';

	let size = 1000;
	let unit = 10;
	let pnt = size / unit;
	let scale = 2 * pnt;

	let squares = size / scale - 1;
</script>

<svg
	version="1.1"
	baseProfile="full"
	xmlns="http://www.w3.org/2000/svg"
	xmlns:xlink="http://www.w3.org/1999/xlink"
	viewBox="0 0 1000 1000"
	id="simple-grid"
	width="90vmin"
	height="90vmin"
>
	<rect x="0" y="0" width={size} height={size} />

	{#each Array(squares) as _, i}
		{#each Array(squares) as _, j}
			<Square x={pnt + i * scale} y={pnt + j * scale} {scale} />
		{/each}
	{/each}

	<AlmostHexagon x={pnt} y={pnt} {scale} />
	<AlmostHexagon x={pnt + scale} y={pnt} {scale} />
	<AlmostHexagon x={pnt + 2 * scale} y={pnt} {scale} />
	<AlmostHexagon x={pnt + 3 * scale} y={pnt} {scale} />

	<AlmostHexagon x={pnt + (1 / 2) * scale} y={pnt + (3 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + scale + (1 / 2) * scale} y={pnt + (3 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + 2 * scale + (1 / 2) * scale} y={pnt + (3 / 4) * scale} {scale} />

	<AlmostHexagon x={pnt} y={pnt + (6 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + scale} y={pnt + (6 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + 2 * scale} y={pnt + (6 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + 3 * scale} y={pnt + (6 / 4) * scale} {scale} />

	<AlmostHexagon x={pnt + (1 / 2) * scale} y={pnt + (9 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + scale + (1 / 2) * scale} y={pnt + (9 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + 2 * scale + (1 / 2) * scale} y={pnt + (9 / 4) * scale} {scale} />

	<AlmostHexagon x={pnt} y={pnt + (12 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + scale} y={pnt + (12 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + 2 * scale} y={pnt + (12 / 4) * scale} {scale} />
	<AlmostHexagon x={pnt + 3 * scale} y={pnt + (12 / 4) * scale} {scale} />
</svg>

<footer>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
</footer>

<style>
	svg {
		fill: beige;
		stroke: darkgoldenrod;
		stroke-width: 2%;
		fill-opacity: 70%;
	}

	#simple-grid :global(.square) {
		fill: palevioletred;
		stroke: darkorchid;
		stroke-width: 5px;
	}

	#simple-grid :global(.square):nth-of-type(2n) {
		fill: lightsalmon;
	}

	#simple-grid :global(.hexagon) {
		fill: skyblue;
		stroke: darkcyan;
		stroke-width: 5px;
	}

	#simple-grid :global(.hexagon):nth-of-type(2n) {
		fill: paleturquoise;
	}

	#simple-grid :global(.hexagon):nth-of-type(3n) {
		fill: lightsteelblue;
	}

	#simple-grid :global(.hexagon):nth-of-type(4n) {
		fill: lightblue;
	}

	#simple-grid :global(.hexagon):hover {
		fill: cyan;
		stroke: azure;
	}
</style>

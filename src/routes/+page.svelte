<script lang="ts">
	import Hexagon from './hexagon.svelte';
	import Square from './square.svelte';
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
	<rect x="0" y="0" width="1000" height="1000" />
	<Square x={100} y={100} scale={250} />
	<Hexagon x={100} y={100} scale={250} />
	<Hexagon
		x={100 + (250 / 4) * (2 + Math.sqrt(3)) - (250 / 4) * (2 - Math.sqrt(3))}
		y={100}
		scale={250}
	/>
	<Hexagon
		x={100 + ((250 / 4) * 2 - (250 / 4) * (2 - Math.sqrt(3)))}
		y={100 + (250 / 4) * 3}
		scale={250}
	/>
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

	#simple-grid :global(.hexagon) {
		fill: skyblue;
		stroke: darkcyan;
		stroke-width: 5px;
	}

	#simple-grid :global(.hexagon):nth-of-type(2n) {
		fill: lightcyan;
	}

	#simple-grid :global(.hexagon):nth-of-type(3n) {
		fill: paleturquoise;
	}

	#simple-grid :global(.hexagon):nth-of-type(4n) {
		fill: cadetblue;
	}

	#simple-grid :global(.hexagon):nth-of-type(5n) {
		fill: lightsteelblue;
	}

</style>

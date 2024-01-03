<script>
	// [center, 12 o'clock, 2 o'clock, 4 o'clock, ...]
	const points = [
		{ x: 100, y: 100 },
		{ x: 100, y: 0 },
		{ x: 186.6, y: 50 },
		{ x: 186.6, y: 150 },
		{ x: 100, y: 200 },
		{ x: 13.4, y: 150 },
		{ x: 13.4, y: 50 }
	];
</script>

<h1>Sample game board</h1>
<svg id="gameboard-svg" viewBox="0 0 200 200">
	<!-- Define a 3 axis hexagonal grid -->
	<!-- Fill in cells and borders at the specified coordinates -->
	<!-- Locate polygons at filled cells to attach event handling -->
	<g class="cell">
		<polygon
			points={points
				.slice(1)
				.map(({ x, y }) => `${x},${y}`)
				.join(' ')}
		/>

		<circle cx={points[0].x} cy={points[0].y} r="1" />
		<line class="axis sixty" x1={points[1].x} y1={points[1].y} x2={points[2].x} y2={points[2].y} />
		<line
			class="axis vertical"
			x1={points[2].x}
			y1={points[2].y}
			x2={points[3].x}
			y2={points[3].y}
		/>
		<line class="axis thirty" x1={points[3].x} y1={points[3].y} x2={points[4].x} y2={points[4].y} />
		<line class="axis sixty" x1={points[4].x} y1={points[4].y} x2={points[5].x} y2={points[5].y} />
		<line
			class="axis vertical"
			x1={points[5].x}
			y1={points[5].y}
			x2={points[6].x}
			y2={points[6].y}
		/>
		<line class="axis thirty" x1={points[6].x} y1={points[6].y} x2={points[1].x} y2={points[1].y} />
	</g>
</svg>

<style>
	svg {
		--side: 70vmin;
		align-self: center;
		width: var(--side);
		height: var(--side);
		margin: 2%;
		background-color: beige;
	}

	.cell {
		fill: azure;
		stroke: darkslategray;
		stroke-width: 2%;
	}

	.axis {
		stroke-dasharray: 5 3;
	}

	.cell .sixty {
		stroke: chocolate;
	}

	.cell .vertical {
		stroke: darkseagreen;
	}

	.cell .thirty {
		stroke: royalblue;
	}
</style>

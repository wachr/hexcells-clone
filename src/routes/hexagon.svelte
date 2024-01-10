<script lang="ts">
	export let x = 0;
	export let y = 0;
	export let side = 100;
	$: radius = side / 4;
	$: points = [
		[2 * radius, 0],
		[(2 + Math.sqrt(3)) * radius, radius],
		[(2 + Math.sqrt(3)) * radius, 3 * radius],
		[2 * radius, 4 * radius],
		[(2 - Math.sqrt(3)) * radius, 3 * radius],
		[(2 - Math.sqrt(3)) * radius, radius]
	]
		// .map((point) => point.map((n) => Math.trunc(n)))
		.map(([x1, y1]) => [x + x1, y + y1])
		.map((point) => point.join(','))
		.join(' ');
</script>

<polygon class="hexagon" {points} />

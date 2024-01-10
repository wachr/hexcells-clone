<script lang="ts">
	export let x = 0;
	export let y = 0;
	export let scale = 100;
	let halfRadius = scale / 4;
	let points = [
		[2 * halfRadius, 0],
		[(2 + Math.sqrt(3)) * halfRadius, halfRadius],
		[(2 + Math.sqrt(3)) * halfRadius, 3 * halfRadius],
		[2 * halfRadius, 4 * halfRadius],
		[(2 - Math.sqrt(3)) * halfRadius, 3 * halfRadius],
		[(2 - Math.sqrt(3)) * halfRadius, halfRadius]
	]
		// .map((point) => point.map((n) => Math.trunc(n)))
		.map(([x1, y1]) => [x + x1, y + y1])
		.map((point) => point.join(','))
		.join(' ');
</script>

<polygon class="hexagon" {points} />

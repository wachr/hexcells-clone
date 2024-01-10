<script lang="ts">
	export let x = 0;
	export let y = 0;
	export let scale = 100;
	let halfRadius = scale / 4;
	let points = [
		[2, 0],
		[4, 1],
		[4, 3],
		[2, 4],
		[0, 3],
		[0, 1]
	]
		.map(([x1, y1]) => [halfRadius * x1, halfRadius * y1])
		.map(([x1, y1]) => [x + x1, y + y1])
		.map((point) => point.join(','))
		.join(' ');
</script>

<polygon class="hexagon almost" {points} />

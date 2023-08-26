<script>
	import { Application } from '@splinetool/runtime';
	import { onMount } from 'svelte';

	onMount(async () => {
		const canvas = document.getElementById('canvas3d');
		const app = new Application(canvas);
		app.load('https://prod.spline.design/15Djxyt0ppBn9MA0/scene.splinecode');
	});
</script>

<div class="h-full min-h-screen">
	<canvas id="canvas3d" />
</div>

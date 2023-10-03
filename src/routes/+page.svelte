<script>
	import { Application } from '@splinetool/runtime';
	import { onMount } from 'svelte';
	import Typewriter from 'svelte-typewriter';
	import { Jumper } from 'svelte-loading-spinners';
	let loading = true;
	onMount(async () => {
		const canvas = document.getElementById('canvas3d');
		if (canvas !== null) {
			const app = new Application(canvas);
			app.load('https://prod.spline.design/i1vVSiQte1dh6fwm/scene.splinecode').then(() => {
				showScreen();
				loading = false;
			});
		}
		// intervalSet();
	});
	const showScreen = () => {
			hiddenClass = 'hidden';
	}
	$: hiddenClass = loading ? '' : 'hidden';
</script>

<div class="h-full min-h-screen flex bg-black items-center justify-center {hiddenClass}">
	<div>
		<Jumper size="200" color="white" unit="px" duration="1s" />
	</div>
</div>

<div class="h-full min-h-screen relative">
	<canvas class="absolute min-h-screen" id="canvas3d" />
	<div class="absolute top-1/4 right-1/4 transform translate-y-[-50%]">
		<div class="text-center">
			<h1 class="text-white text-7xl font-bold">Hello!</h1>
		</div>
		<div class="text-center">
			{#if loading == false}
			<Typewriter delay={1000} interval={200}>
				<h1 class="text-white py-2 text-7xl font-bold">I'm Seth</h1>
			</Typewriter>
			{/if}
		</div>
	</div>
	<div class="absolute top-1/2 right-5 transform translate-y-[-50%]">
		<div class="text-center p-4">
			<h4 class="text-white py-2 text-2xl font-bold d-inline">
				{#if loading == false}
				<Typewriter delay={2800} interval={200}>
					<a href="https://github.com/sethmorton">Github | </a><a
						href="https://www.linkedin.com/in/seth-morton-118574242/"
						>LinkedIn |
					</a><a
						href="https://drive.google.com/file/d/1mM4cYNtaboo-0MOkQpJ2jQ7TrZR4JsJk/view?usp=sharing"
						>Resume</a
					>
				</Typewriter>
				{/if}
			</h4>
		</div>
	</div>
</div>

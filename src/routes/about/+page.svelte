<script>
	import { fabric } from 'fabric';
	import { onMount } from 'svelte';
	console.log('fabric: ', fabric);

	onMount(() => {
		var canvas = new fabric.Canvas('c');

		// create a rectangle object
		var rect = new fabric.Rect({
			left: 50,
			top: 50,
			fill: 'red',
			width: 20,
			height: 20
		});

		var text = new fabric.Text('hello world', { left: 100, top: 100 });
		var anotherItalicText = new fabric.Text('another italic text', {
			fontStyle: 'italic',
			fontSize: 14,
			fontFamily: 'Hoefler Text',
			left: 10,
			top: 10
		});
		canvas.add(anotherItalicText);

		// "add" rectangle onto canvas
		canvas.add(rect);

		canvas.on('mouse:down', function (options) {
			if (options.target) {
				console.log('an object was clicked! ', options.target.type);
			}
		});
	});
</script>

<h1>about</h1>
<canvas id="c" width="200" height="200"></canvas>

<style>
	#c {
		border: 2px solid gray;
	}
</style>

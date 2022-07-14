<script lang="ts">
	import Inner from './Inner.svelte';
	import CustomButton from './CustomButton.svelte';

	let name: string = 'world';

	let a = 1;
	let b = 2;

	function handleMessage(event: any) {
		alert(event.detail.text);
	}

	function handleClick() {
		alert('Hello ' + name);
	}
</script>

<h1>Welcome to SvelteKit</h1>

<Inner on:someEvent={handleMessage} />

<CustomButton on:click={handleClick} />

<input bind:value={name} />
<h3>Hello {name}</h3>

<div>
	<label>
		<input type="number" bind:value={a} min="0" max="10" />
		<input type="range" bind:value={a} min="0" max="10" />
	</label>

	<label>
		<input type="number" bind:value={b} min="0" max="10" />
		<input type="range" bind:value={b} min="0" max="10" />
	</label>

	<p>{a} + {b} = {a + b}</p>
</div>

<style>
	label {
		display: flex;
	}
	input,
	p {
		margin: 6px;
	}
</style>

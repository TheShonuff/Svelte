<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function sayHello() {
		dispatch('someEvent', {
			text: 'Hello'
		});
	}
</script>

<button on:click|once={sayHello}>Click to say hello</button>

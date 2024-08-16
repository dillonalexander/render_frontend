<script>
	import Greeting from './Greeting.svelte';
	export let name = 'world';  // Default value for the name variable

	$: greetingMessage = name.length > 5 ? "That's a long name!" : "Nice to meet you!";
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<input bind:value={name} placeholder="Enter your name" />
	<p>{greetingMessage}</p>
	<Greeting {name} />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	input {
		margin-top: 20px;
		padding: 10px;
		font-size: 1em;
		width: 100%;
		box-sizing: border-box;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

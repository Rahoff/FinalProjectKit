<script>
    import { finalClass, finalName, finalGender, finalRace } from '$lib/stores';
    import NameAndGender from '$lib/nameAndGender.svelte';
	import RaceAndClass from '$lib/raceAndClass.svelte';
	import Generator from '$lib/Generator.svelte';

    let steps = [
		{ text: 'Name'},
		{ text: 'Sex' },
		{ text: 'Race' },
		{ text: 'Class'}
	]

    let newName = $finalName.valueOf();
	let generate = false;

</script>
<h1>This application will allow you to generate a character.
All you need to do is pick a name and make a few selections from the following options.
</h1>

<NameAndGender/>
<RaceAndClass/>

{#if newName != undefined}
	<button on:click={ ()=> generate = true }>Roll character</button>
{/if}
{#if generate}
	<Generator/>
    <button on:click={ ()=> generate=false }>Reroll this one</button>
{/if}


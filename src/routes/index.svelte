<script>
    import { finalClass, finalName, finalGender, finalRace } from '$lib/stores';
    import NameAndGender from '$lib/nameAndGender.svelte';
	import RaceAndClass from '$lib/raceAndClass.svelte';
	import Generator from '$lib/Generator.svelte';
	import SaveFile, {reRoll,  saveCharacter, printCharacter } from '$lib/saveFile.svelte';
	


    let newName = $finalName.valueOf();
	let newClass = $finalClass.valueOf();
	let newGender = $finalGender.valueOf();
	let newRace = $finalRace.valueOf();
	let generateCharacter = false;




</script>
<h1>This application will allow you to generate a character.
All you need to do is pick a name and make a few selections from the following options.
</h1>

<NameAndGender/>
<RaceAndClass/>

{#if $finalName != undefined }
	<button on:click={ ()=> generateCharacter = true } >Roll character</button>
{/if}
{#if generateCharacter}
	<div id="printArea">
		<Generator/>
	</div>
    <button on:click={ ()=> reRoll()}>Reroll this one</button>
	<button on:click={ ()=> printCharacter('printArea') }>Print Sheet</button>
	<button on:click={ ()=> saveCharacter('printArea') }>Save as text</button>
{/if}
<style>
    div{
		position: absolute; left: 500px; top: 150px;
		background-color: white;
		width: 600px;
	}
</style>


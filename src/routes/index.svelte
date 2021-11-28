<script>
    import { finalClass, finalName, finalGender, finalRace } from '$lib/stores';
    import NameAndGender from '$lib/nameAndGender.svelte';
	import RaceAndClass from '$lib/raceAndClass.svelte';
	import Generator from '$lib/Generator.svelte';
	import {reRoll,  saveCharacter, printCharacter } from '$lib/saveFile.svelte';
	

	let generateCharacter = false;

</script>
<h1>This application will allow you to generate a character.
All you need to do is pick a name and make a few selections from the following options.
</h1>

<NameAndGender/>
<RaceAndClass/>

{#if $finalName && $finalClass && $finalGender && $finalRace }
	<button id="rollButton" on:click={ ()=> generateCharacter = true } >Roll character</button>
{/if}

{#if generateCharacter}
	<div id="printArea">
		<Generator/>
	</div>
	<div id="buttonArea">
		<button on:click={ ()=> reRoll()}>Reroll this one</button>
		<button on:click={ ()=> printCharacter('printArea') }>Print</button>
		<button on:click={ ()=> saveCharacter('printArea') }>Save</button>
	</div>

{/if}
<style>
    #printArea{
		position: absolute; left: 500px; top: 150px;
		background-color: white;
		width: 600px;
		text-align: center;
	}
	#buttonArea{
		position:absolute;left: 40%; top: 75%
		
	}
	#rollButton{
		position:absolute; left: 100px; top: 410px;
	}
	button  {
		background-color: silver;
		border-radius: 12px;
		cursor: pointer;
		border-color: silver;
		border-style: outset;
		border-width: 5px;
	}
</style>


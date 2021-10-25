<script>
    import { finalName } from '$lib/stores';
    import { finalRace } from '$lib/stores';
    import { finalClass } from '$lib/stores';
    import { finalGender } from '$lib/stores';

    let newName, newRace, newClass, newGender;

    //this gets the array of ability scores.
    let abilityArray = new Array(6); 
    for (let i=0; i < abilityArray.length; i ++ ){
        abilityArray[i] = Math.floor((Math.random()*6) +1) +  Math.floor((Math.random() * 6) + 1) +  Math.floor((Math.random() * 6) + 1);
    }
    abilityArray = abilityArray.sort(function(a, b){return b-a});
    console.log(abilityArray);
    finalName.subscribe( name =>{ newName = name.val });
    finalRace.subscribe( race =>{ newRace = race.val });
    finalClass.subscribe( job =>{ newClass = job.val });
    finalGender.subscribe( gender =>{ newGender = gender.val });

</script>
<h1>Name: { newName } </h1>
<h2>Sex: { newGender }</h2>
<h2>Race: { newRace }</h2>
<h2>Class: { newClass }</h2>
<ul>
    {#if newClass === "Fighter"}
    <li>Strength = { abilityArray[0] }</li>
    <li>Dexterity = { abilityArray[2] }</li>
    <li>Constitution = { abilityArray[1] }</li>
    <li>Intelligence = { abilityArray[3]} </li>
    <li>Wisdom = { abilityArray[4] } </li>
    <li>Charisma = { abilityArray[5] } </li>
    {/if}
    {#if newClass === "Priest"}
    <li>Strength = { abilityArray[3] }</li>
    <li>Dexterity = { abilityArray[5] }</li>
    <li>Constitution = { abilityArray[2] }</li>
    <li>Intelligence = { abilityArray[4]} </li>
    <li>Wisdom = { abilityArray[0] } </li>
    <li>Charisma = { abilityArray[1] } </li>
    {/if}
    {#if newClass === "Wizard"}
    <li>Strength = { abilityArray[4] }</li>
    <li>Dexterity = { abilityArray[1] }</li>
    <li>Constitution = { abilityArray[2] }</li>
    <li>Intelligence = { abilityArray[0]} </li>
    <li>Wisdom = { abilityArray[3] } </li>
    <li>Charisma = { abilityArray[5] } </li>
    {/if}
    {#if newClass === "Rogue"}
    <li>Strength = { abilityArray[1] }</li>
    <li>Dexterity = { abilityArray[0] }</li>
    <li>Constitution = { abilityArray[3] }</li>
    <li>Intelligence = { abilityArray[2]} </li>
    <li>Wisdom = { abilityArray[4] } </li>
    <li>Charisma = { abilityArray[5] } </li>
    {/if}
</ul>>

<style>
	h1 {
		color: blue;
	}
    h2{
        color: blue;
    }
    ul{
        color: darkcyan;
        background-color: black;
    }
</style>
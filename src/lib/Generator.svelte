<script>
    import { finalName } from '$lib/stores';
    import { finalRace } from '$lib/stores';
    import { finalClass } from '$lib/stores';
    import { finalGender } from '$lib/stores';

    let newName, newRace, newClass, newGender, hitPoints;

    //this gets the array of ability scores.
    let abilityArray = new Array(6); 
    for (let i=0; i < abilityArray.length; i ++ ){
        abilityArray[i] = Math.floor((Math.random()*6) +1) +  Math.floor((Math.random() * 6) + 1) +  Math.floor((Math.random() * 6) + 1);
    }
    abilityArray = abilityArray.sort(function(a, b){return b-a});

    finalName.subscribe( name =>{ newName = name.val });
    finalRace.subscribe( race =>{ newRace = race.val });
    finalClass.subscribe( job =>{ newClass = job.val });
    finalGender.subscribe( gender =>{ newGender = gender.val });

    if(newClass == "Fighter"){
        hitPoints =  Math.floor(Math.random()*10 + 1);
        if(hitPoints == 1){
            hitPoints++;
        }
        if(abilityArray[1] == 12 || abilityArray[1] == 13){
            hitPoints = hitPoints + 1;
        }
        if(abilityArray[1] == 14 || abilityArray[1] == 15){
            hitPoints = hitPoints + 2;
        }
        if(abilityArray[1] == 16 || abilityArray[1] == 17){
            hitPoints = hitPoints + 3;
        }
        if(abilityArray[1] == 18){
            hitPoints = hitPoints + 4;
        }
    }
    if (newClass == "Priest"){
        hitPoints =  Math.floor(Math.random()*8 + 1);
        if(hitPoints == 1){
            hitPoints++;
        }
        if(abilityArray[2] == 12 || abilityArray[2] == 13){
            hitPoints = hitPoints + 1;
        }
        if(abilityArray[2] == 14 || abilityArray[2] == 15){
            hitPoints = hitPoints + 2;
        }
        if(abilityArray[2] == 16 || abilityArray[2] == 17){
            hitPoints = hitPoints + 3;
        }
        if(abilityArray[2] == 18){
            hitPoints = hitPoints + 4;
        }
    }
    if(newClass == "Wizard"){
        hitPoints =  Math.floor(Math.random()*4 + 1);
        if(hitPoints == 1){
            hitPoints++;
        }
        if(abilityArray[2] == 12 || abilityArray[2] == 13){
            hitPoints = hitPoints + 1;
        }
        if(abilityArray[2] == 14 || abilityArray[2] == 15){
            hitPoints = hitPoints + 2;
        }
        if(abilityArray[2] == 16 || abilityArray[2] == 17){
            hitPoints = hitPoints + 3;
        }
        if(abilityArray[2] == 18){
            hitPoints = hitPoints + 4;
        }
    }
    if(newClass == "Rogue"){
        hitPoints =  Math.floor(Math.random()*6 + 1);
        if(hitPoints == 1){
            hitPoints++;
        }
        if(abilityArray[3] == 12 || abilityArray[3] == 13){
            hitPoints = hitPoints + 1;
        }
        if(abilityArray[3] == 14 || abilityArray[3] == 15){
            hitPoints = hitPoints + 2;
        }
        if(abilityArray[3] == 16 || abilityArray[3] == 17){
            hitPoints = hitPoints + 3;
        }
        if(abilityArray[3] == 18){
            hitPoints = hitPoints + 4;
        }
    }

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
        <li>Intelligence = { abilityArray[3] } </li>
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
</ul>
<h3>
    Hit Points = { hitPoints }
</h3>
   
<style>
	h1 {
		color: darkcyan;
	}
    h2{
        color: darkcyan;
    }
    h3{
        color: darkcyan;
    }
    ul{
        color: darkcyan;
        background-color: white;
        display: table;
        margin:  0 auto;
    }

</style>
<script>
    import { finalClass } from './stores.js';
    import { finalRace } from './stores.js';

    let selected = undefined;
    let selectedClass = undefined;
    //export let charRace = undefined;
    //export let charClass = undefined;

    let race =[
        { id: 1, text: "Choose Race"},
        { id: 2, text: "Human"},
        { id: 3, text: "Elf"},
        { id: 4, text: "Dwarf"},
        { id: 5, text: "Half Elf"}
    ];

    let profesion = [
        { id: 1, text: "Choose Class"},
        { id: 2, text: "Priest"},
        { id: 3, text: "Rogue"},
        { id: 4, text: "Fighter"},
        { id: 5, text: "Wizard"}
    ];
    function changedRace(val){
        $finalRace = { val };   
    }
    function changedClass(val){
        $finalClass = { val };
    }

    
</script>

<!-- <h1>Race: {selected ? selected.text : ['Waiting...']} <br> Class: {selectedClass ? selectedClass.text : ['waiting...']}</h1> -->

<label>
    Select your race
    <select bind:value={selected} on:change={changedRace(selected.text)}>
        {#each race as raceChoice}
            <option value={raceChoice}>
                {raceChoice.text}
            </option>
        {/each}
    </select>
</label>
<label>
    Select your class: 
    <select bind:value={selectedClass} on:change={changedClass(selectedClass.text)}>
        {#each profesion as choice}
            <option value = {choice}>
                {choice.text}
            </option>
        {/each}
    </select>
</label>

<style> 
    *{
        background-color:black;
        color: darkcyan;
        width:300px;
        min-height: fit-content;   
    }
    label{        
        font-weight: bolder;
    }
    select{
        border-color: black;
    }

</style>
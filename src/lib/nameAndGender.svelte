<script>

    import { finalName } from "./stores.js";
    import { finalGender } from "./stores.js";

    let name = "";
    
    let selected;
    let genders = [
        { id:1, text: "Choose One" },
        { id:2, text: "Male" },
        { id:3, text: "Female" }
    ];
    function updateName(val) {
        $finalName = {val};
    }
    function updateGender(val){
        $finalGender = {val}
    }

</script>

<label>Enter a name
    <input type="text" bind:value={name} on:change={updateName(name)}>
</label>
<label>
    Select your gender
    <select bind:value={selected} on:change= { updateGender(selected.text) }>
        {#each genders as gender}
            <option value={gender}>
                {gender.text}
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
    input{
        border-color: black;
        background-color:rgb(40, 40, 40);
    }
    select{
        border-color: black;
    }


</style>
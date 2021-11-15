<script context = "module">
	import { saveAs } from 'file-saver';
	import { finalName } from '$lib/stores';
	
    export function saveCharacter(printArea){
		let newName;
		finalName.subscribe( name =>{ newName = name.val });
		var character = document.getElementById(printArea).innerText;
		var fileName = newName + ".txt";
		console.log(character);
        var blob = new Blob([character], { type: "text/plain;charset=utf-8" });
		saveAs(blob, fileName);
    }
    export function reRoll(){
		window.location.reload(false);
	}
    export function printCharacter(printArea){
		var printContents = document.getElementById(printArea).innerHTML;
		var original = document.body.innerHTML;
		document.body.innerHTML = printContents;
		window.print();
		document.body.innerHTML = original;
	}
</script>
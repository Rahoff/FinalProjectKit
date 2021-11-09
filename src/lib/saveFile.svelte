<script context = "module">
    export function saveCharacter(){
        console.log("Its verking");
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
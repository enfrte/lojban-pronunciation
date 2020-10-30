<script>
    export let sound;
    export let filename;
	export let customClass = '';

	function play(filename) {
		const audioFile = 'audio/'+filename+'.mp3';
		new Audio(audioFile).play();
	}
</script>

<button class="key-button {customClass ? customClass : 'regular-key'}" type="button" on:click={play(filename)}>{sound}</button>

<style>

.key-button {
    box-sizing: border-box;
    font-size: 24px;
    text-align: center;
    color: #555;
    cursor: pointer;
    margin: 8px;
    height: 80px;
    border-color: #333;
    border-style: solid;
    border-width: 1px;
    border-radius: 3px;
    font-family: sans-serif;
}

.regular-key {
	width: 80px
}

.wider-key {
	width: 120px
}

@media (max-width: 576px) {
    .key-button {
        margin: 4px;
        height: 50px;
    }

    .regular-key {
	width: 50px
    }

    .wider-key {
        width: 90px
    }

}
</style>
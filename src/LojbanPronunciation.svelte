<svelte:options tag="audio-button" />

<script>
    import AudioButton from "./AudioButton.svelte";

    let alphabet = true;

    function handleMenu(selection) {
        alphabet = (selection === 'alphabet') ? true : false;
    }
</script>

<div class="lojban-keyboard-container">

    <a href="https://www.youtube.com/watch?v=xIYOyiAE-sY">To do: Build a component https://www.youtube.com/watch?v=xIYOyiAE-sY</a>

    <p>Voiced by Matt Arnold</p>

    <div class="sound-menu">
        <button on:click={() => { handleMenu('alphabet') }}>Alphabet</button>
        <button on:click={() => { handleMenu('') }}>Dipthongs</button>
    </div>

    {#if alphabet}
        <div class="lojban-keyboard-row" id="alphabet">
            <AudioButton filename="a" sound="a" />
            <AudioButton filename="b" sound="b" />
            <AudioButton filename="c" sound="c" />
            <AudioButton filename="d" sound="d" />
            <AudioButton filename="e" sound="e" />
            <AudioButton filename="f" sound="f" />
            <AudioButton filename="g" sound="g" />
            <AudioButton filename="apos" sound="'" />
            <AudioButton filename="i" sound="i" />
            <AudioButton filename="j" sound="j" />
            <AudioButton filename="k" sound="k" />
            <AudioButton filename="l" sound="l" />
            <AudioButton filename="m" sound="m" />
            <AudioButton filename="n" sound="n" />
            <AudioButton filename="o" sound="o" />
            <AudioButton filename="p" sound="p" />
            <AudioButton filename="r" sound="r" />
            <AudioButton filename="s" sound="s" />
            <AudioButton filename="t" sound="t" />
            <AudioButton filename="u" sound="u" />
            <AudioButton filename="v" sound="v" />
            <AudioButton filename="x" sound="x" />
            <AudioButton filename="y" sound="y" />
            <AudioButton filename="z" sound="z" />
            <AudioButton filename="lojban" sound="lojban" customClass="wider-key" />
        </div>
    {:else}
        <div class="lojban-keyboard-row" id="dipthongs">
            <AudioButton filename="ai" sound="ai" />
            <AudioButton filename="au" sound="au" />
            <AudioButton filename="ei" sound="ei" />
            <AudioButton filename="ia" sound="ia" />
            <AudioButton filename="ie" sound="ie" />
            <AudioButton filename="ii" sound="ii" />
            <AudioButton filename="io" sound="io" />
            <AudioButton filename="iu" sound="iu" />
            <AudioButton filename="iy" sound="iy" />
            <AudioButton filename="oi" sound="oi" />
            <AudioButton filename="ua" sound="ua" />
            <AudioButton filename="ue" sound="ue" />
            <AudioButton filename="ui" sound="ui" />
            <AudioButton filename="uo" sound="uo" />
            <AudioButton filename="uu" sound="uu" />
            <AudioButton filename="uy" sound="uy" />
        </div>
    {/if}

</div>

<style>

    .sound-menu {
        display: flex;
        flex-wrap: wrap;
        max-width: 100%;
    }

    .sound-menu button {
        font-size: 24px;
        background-color: #333;
        color: whitesmoke;
        margin: 8px;
        border: none;
    }

    .lojban-keyboard-container {
        max-width: 800px;
        background-color: whitesmoke;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100%;
        margin: auto;
    }

    .lojban-keyboard-row {
        display: flex;
        flex-wrap: wrap;
        max-width: 100%;
    }

    @media (max-width: 576px) {
        .sound-menu button {
            font-size: 18px;
        }
    }

</style>
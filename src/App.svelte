<script>
    import Keyboard from "./components/Keyboard.svelte";

    let logs = [];

    function noteOn(event) {
        logs = [`Note ${event.detail} was pressed!`, ...logs];
    }

    function noteOff(event) {
        logs = [`Note ${event.detail} was released!`, ...logs];
    }
</script>

<svelte:head>
    <title>Svelte Piano</title>
</svelte:head>

<Keyboard octaves={3} on:noteon={noteOn} on:noteoff={noteOff} />

{#each logs as log}
    <div>{log}</div>
{/each}

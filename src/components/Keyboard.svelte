<script>
    export let octaves = 2;
    export let middleC = 60;

    import Key from "./Key.svelte";
    let keys;

    $: keys = [...Array(octaves * 12 + 1).keys()].map(
        (i) => i + (middleC - Math.floor(octaves / 2) * 12)
    );
</script>

<div>
    {#each keys as note}
        <Key noteNum={note} on:noteon on:noteoff />
    {/each}
</div>

<style>
    div {
        display: flex;
        justify-content: center;
        overflow: auto;
        padding: 8px;
        height: 192px;
    }
</style>

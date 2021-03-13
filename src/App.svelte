<script>
    import Letter from './Letter.svelte';

    let value = '';
    let active = false;

    $: {
        if (value) {
            active = false;
        }
    }
</script>

<main>
    <input type="text" bind:value />
    <button on:click={() => (active = true)}>Run</button>

    {#if active}
        <div>
            {#each value as letter, i}
                <Letter count={i + 1}>{letter}</Letter>
            {/each}
        </div>
    {/if}
</main>

<style>
    main {
        border: 2px solid #454545;
        padding: 2rem;
        border-radius: 20px;
        width: 50vw;
        margin: 20vh auto;
    }
</style>

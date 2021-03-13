<script>
    import { onMount } from 'svelte';

    export let count = 1;
    export let active = false;

    onMount(() => {
        setTimeout(() => {
            active = true;
        }, count * 200);
    });
</script>

<span class:active>
    <slot />
</span>

<style>
    @keyframes appear {
        80% {
            color: rebeccapurple;
        }

        to {
            transform: scale(1) rotate(0deg);
            color: hotpink;
        }
    }

    span {
        transform: scale(0) rotate(30deg);
        color: crimson;
        text-transform: uppercase;
        font-size: 40px;
        display: inline-block;
    }

    .active {
        animation: appear 0.3s ease-in-out forwards;
    }
</style>

<script>
    import { fade } from 'svelte/transition'
    export let css;
</script>

<div in:fade="{{duration:350}}" out:fade="{{duration:250}}" >
    <p>CSS rule successfully copied!<br><br>{css}</p>
</div>

<style>
    div {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(0, 0, 0, 0.75);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }

    p {
        padding: 2rem;
        border-radius: 4px;
        background-color: #fff;
        color: #0a0a0a;
        max-width: 75%;
    }
</style>
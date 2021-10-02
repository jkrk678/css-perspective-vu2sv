<script>
    export let text;
</script>

<button type="button" on:click>{text}</button>

<style>
    button {
        background-color: #8d81f3;
        color: #fff;
        display: inline-block;
        font-size: 20px;
        padding: 10px;
        outline: none;
        border: none;
        cursor: pointer;
        transition-property: all;
        transition-duration: 150ms;
    }

    button:hover {
        border-radius: 10px;
    }
</style>
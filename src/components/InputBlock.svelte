<script>
    export let property;
    export let quantity;
    export let unit;
    export let value;
    export let id;
    export let min;
    export let max;
</script>

<label for={id}>{property}: {quantity}{unit}</label>
<input bind:value={value} id={id} type="range" min={min} max={max} />

<style>
    label {
        display: block;
        color: #fff;
    }

    input {
        display: block;
        margin-bottom: 10px;
        width: 100%;
        cursor: pointer;
    }
</style>
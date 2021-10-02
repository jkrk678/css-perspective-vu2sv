<main>
    <slot></slot>
</main>

<style>
    main {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        height: 420px;
        max-width: 768px;
        margin: 0 auto;
        font-family: monospace, sans-serif;
        font-size: 22px;
    }

    @media (max-width: 1023px) {
        main {
            flex-direction: column;
            height: auto;
            justify-content: center;
        }
    }
</style>
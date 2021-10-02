<script>
    import Title from './components/Title.svelte'
    import Frame from './components/Frame.svelte'
    import InputsSection from './components/InputsSection.svelte'
    import InputBlock from './components/InputBlock.svelte'
    import StyledBox from './components/StyledBox.svelte'
    import ButtonContainer from './components/ButtonContainer.svelte'
    import Button from './components/Button.svelte'
    import Toast from './components/Toast.svelte'

    let p = 100;
    let x = 0;
    let y = 0;
    let z = 0;

    $:cssString = `transform: perspective(${p}px) rotateX(${x}deg) rotateY(${y}deg) rotateZ(${z}deg);`;

    let visible = false;

    const reset = () => {
        p = 100;
        x = 0;
        y = 0;
        z = 0;
    }

    const copy = () => {
        const el = document.createElement('textarea');

        el.setAttribute('readonly', '');
        el.style.position = 'absolute';
        el.style.left = '-9999px';
        el.value = cssString;
        document.body.appendChild(el);
        el.select();
        document.execCommand('copy');
        document.body.removeChild(el);
        visible = true;
        setTimeout(() => {visible = false}, 3000)
    }
</script>

{#if visible}
    <Toast css={cssString} />
{/if}

<Title title="CSS Perspective Playground" />
<Frame>
    <InputsSection>
        <InputBlock bind:value={p} id="p" property="perspective" quantity={p} unit="px" min="0" max="999"/>
        <InputBlock bind:value={x} id="x" property="rotateX" quantity={x} unit="deg" min="-180" max="180"/>
        <InputBlock bind:value={y} id="y" property="rotateY" quantity={y} unit="deg" min="-180" max="180"/>
        <InputBlock bind:value={z} id="z" property="rotateZ" quantity={z} unit="deg" min="-180" max="180"/>
        <ButtonContainer>
            <Button text="Reset" on:click={reset} />
            <Button text="Copy" on:click={copy} />
        </ButtonContainer>
    </InputsSection>


    <section class="output">
      <StyledBox p={p} x={x} y={y} z={z} />
    </section>
</Frame>
<script>
    // @ts-nocheck

    import { tick } from "svelte";
    let value = "";

    async function onInput(event) {
        const input = this;
        let selectionStart = input.selectionStart;
        let selectionEnd = input.selectionEnd;
        value = input.value.toUpperCase();

        await tick();
        input.selectionStart = selectionStart;
        input.selectionEnd = selectionEnd;
    }
</script>

<input type="text" on:input={onInput} bind:value />
<button
    on:click={() => {
        setTimeout(() => {
            console.log("timeout!");
            value = "xxx";
        }, 3000);
    }}>Update Value</button
>

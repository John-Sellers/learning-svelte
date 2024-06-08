<script>
    import { onMount, onDestroy, beforeUpdate, afterUpdate } from "svelte";

    let count = 0;

    onMount(() => {
        console.log("onMount");
    });

    onDestroy(() => {
        console.log("onDestroy");
    });

    beforeUpdate(() => {
        console.log("beforeUpdate");
    });

    afterUpdate(() => {
        console.log("afterUpdate");
    });

    function update() {
        count++;
    }
</script>

{count}
<button on:click={update}>Increment</button>

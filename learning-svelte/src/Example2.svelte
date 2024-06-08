<script>
    import { onMount, onDestroy } from "svelte";

    let src;

    onMount(() => {
        const controller = new AbortController();
        const signal = controller.signal;

        fetch(`https://dog.ceo/api/breeds/image/random`, { signal })
            .then((response) => response.json())
            .then(({ message }) => {
                src = message;
            });
    });
</script>

<img {src} alt="Random Dog" />

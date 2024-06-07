<!-- Dynamic content using Svelte -->

<!-- <script>
    let content = "Hello World";
    let imageUrl = "https://svelte.dev/svelte-logo-horizontal.svg";
</script>

<h1>{content}</h1>

<img src={imageUrl} alt="Svelte Logo" /> -->

<!-- Reactivity using Svelte -->
<!-- <script>
    // How does Svelte know when to update the state?
    // 1. Assignment to a variable -> count = 10;
    // 2. Update statements -> count += 1 or count++/--;
    // 3. Updating/assignment to a property -> obj.count++ or obj.count = 10;
    let count = 0;

    function increment() {
        count++;
    }

    function reset() {
        count = 0;
    }

    function decrement() {
        count--;
    }
</script>

{count}

<button on:click={decrement}>Decrement</button>
<button on:click={reset}>Reset Count</button>
<button on:click={increment}>Increment</button> -->

<!-- Event listeners using Svelte -->
<!-- <script>
    // A function can be used for the event listener or ternary operator
    function onClick() {
        console.log("Clicked!");
    }
</script>

<button
    on:click|preventDefault|stopPropagation={() => console.log("Also Clicked!")}
    >Click me!</button
>

<div on:click={() => console.log("Parent Clicked!")}>
    Parent
    <div on:click|stopPropagation={() => console.log("Child Clicked!")}>
        Child
    </div>
</div> -->

<!-- Reactive Declarations/Statements -->

<!-- Reactive Declarations/Statements
    $: <expression>
    
    Whenever the dependencies of the expression change, the expression will be re-evaluated.
    This is similar to computed properties in libraries like Vue.js.
    It's also similar to the `update` blocks in SvelteKit.
-->

<!-- <script>
    let count = 0;
    let a = 0;
    let b = 0;
    let c = 0;
    let firstname = "";
    let lastname = "";

    $: doubled = count * 2;
    $: fullname = firstname + " " + lastname;
    $: {
        console.log("count is " + count);
    }
    $: sum = a + b + c;
    $: doSomething(a, b, c);

    function doSomething(a, b, c) {
        console.log(a, b, c);
    }
</script> -->

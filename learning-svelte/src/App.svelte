<!-- Dynamic Content Using Svelte -->

<!-- <script>
    let content = "Hello World";
    let imageUrl = "https://svelte.dev/svelte-logo-horizontal.svg";
</script>

<h1>{content}</h1>

<img src={imageUrl} alt="Svelte Logo" /> -->

<!-- Reactivity Using Svelte -->
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

<!-- Event Listeners Using Svelte -->
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

<!-- Tick Function In Svelte -->

<!-- The `tick` function schedules a microtask to be run after the current execution context is done.
    This is useful when you want to defer the re-evaluation of reactive statements.
    For example, if you want to update multiple state variables together, you can wrap them in a function
    and then call `tick` to ensure that all the updates are batched together into a single re-render. -->

<!-- <script>
    import { tick } from "svelte";

    let count = 0;

    $: doubled = count * 2;

    async function increment() {
        count++;
        await tick();
        console.log("After tick:", doubled);
    }

    function decrement() {
        count--;
    }

    function multiply() {
        count = count * count;
    }
    function doSomething() {
        console.log(doubled);
    }

    function reset() {
        count = 0;
    }
</script>

<button on:click={decrement}>-</button>
<button on:click={reset}>Reset Count</button>
<p>{count}</p>
<button on:click={increment}>+</button>
<button on:click={multiply}>Scale</button>
<button on:click={doSomething}>Click Me</button>

<script>
    import { tick } from "svelte";
    import Input from "./Input.svelte";
</script>

<Input /> -->

<!-- Svelte Components & Props -->
<!-- In Svelte, components are reusable parts of a web page. 
    They can take in props (short for properties) that are passed
    to them. These props are like arguments that are used to customize 
    the component. Imagine a component like a TV that has settings (props) 
    like the size of the screen, the color of the TV, and the channels 
    it can display. You can pass these settings to the TV component to 
    make it unique to your needs. The Svelte `<script>` tag is where you
    define the props that the component can take in. The `export` keyword 
    is used to make the props public so they can be passed to the component.
    The props are then used in the component's HTML to display the customized settings. -->
<!-- <script>
    import Component from "./Component.svelte";

    let name = "Svelte";

    const obj = {
        name: "Svelte",
        email: "bNwz3@example.com",
        age: 25,
    };
</script>

<h1>Hello {name}!</h1>
<Component {name} />
<Component name="John" email="john@example.com" />
<Component name={obj.name} email={obj.email} age={obj.age} />
<Component {...obj} /> -->

<!-- Svelte Components Events -->
<!-- <script>
    import Profile from "./Profile.svelte";

    function onSkillPointChanged(event) {
        console.log("onSkillPointChanged", event.detail);
    }
</script>

<Profile
    name="John"
    status="Active"
    on:skillPointChanged={onSkillPointChanged}
/>

<Profile name="Bill" status="Inactive" /> -->

<!-- Class:Directives -->

<!-- <script>
    let profit = 0;

    $: negative = profit < 0;
    $: positive = profit > 0;
    $: neutral = profit === 0;
</script>

<div class:negative class:positive class:neutral>
    {profit}
</div>

<button on:click={() => profit--}>-</button>
<button on:click={() => profit++}>+</button>

<style>
    .neutral {
        color: yellow;
    }
    .positive {
        color: green;
    }
    .negative {
        color: red;
    }
</style> -->

<!-- Binding:Directives -->
<!-- Binding:Directives
    The `bind:` directive is used to create two-way data bindings.
    It allows you to bind a value from a component to a property of an input element.
    When the value of the input changes, it updates the value of the component's property.
    When the property is updated in the component, the value of the input is updated as well. -->
<!-- <script>
    let value = 0;
</script>

<input bind:value type="number" />
<div>value: {value}</div>
<button on:click={() => (value = 0)}>Reset</button> -->

<!-- <script>
    let option = [3]; // Initialize as an array
</script>

<label>
    <input type="checkbox" bind:group={option} name="option" value="1" />1
</label>
<label>
    <input type="checkbox" bind:group={option} name="option" value="2" />2
</label>
<label>
    <input type="checkbox" bind:group={option} name="option" value="3" />3
</label>
<label>
    <input type="checkbox" bind:group={option} name="option" value="4" />4
</label>
<button on:click={() => (option = [])}></button>

Selected Option: {option.join(", ")} -->

<!-- Component Lifecycle -->
<!-- <script>
    import ComponentLifeCycle from "./ComponentLifeCycle.svelte";
    let condition;
</script>

<input type="checkbox" bind:checked={condition} />

{#if condition}
    <ComponentLifeCycle />
{/if} -->

<!-- <script>
    import Example1 from "./Example1.svelte";
    import Example2 from "./Example2.svelte";

    let show = false;
</script>

<input type="checkbox" bind:checked={show} />

{#if show}
    <Example1 />
    <Example2 />
{/if} -->

<!-- {#if} Block -->
<!-- <script>
    let condition1 = true;
    let condition2 = true;
    let condition3 = true;

    function toggleCondition1() {
        condition1 = !condition1;
    }

    function toggleCondition2() {
        condition2 = !condition2;
    }
    function toggleCondition3() {
        condition3 = !condition3;
    }
</script>

<button on:click={toggleCondition1}>Condition: {condition1}</button>
<button on:click={toggleCondition2}>Condition: {condition2}</button>
<button on:click={toggleCondition3}>Condition: {condition3}</button>
<hr />

{#if condition1 && condition2}
    <p>Condition 1 and 2 are true</p>
    {#if condition3}
        <div>Hello</div>
        <p>Condition 3 is true</p>
    {/if}
{:else if condition1}
    <p>Condition 1 is true</p>
{:else if condition2}
    <p>Condition 2 is true</p>
{/if}

<style>
    hr {
        background-color: white;
    }
</style> -->

<!-- {#each} Block -->
<!-- <script>
    let colors = ["red", "green", "blue"];

    function addColor() {
        colors = [...colors, "yellow"];
    }
</script>

<button on:click={addColor}>Add Color</button>
<ul>
    {#each colors as color, index}
        <li style="color: {color}; list-style-type: circle">{color} {index}</li>
    {:else}
        <p>Loading...</p>
    {/each}
</ul> -->

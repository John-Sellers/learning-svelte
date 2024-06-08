<script>
    import { createEventDispatcher } from "svelte";

    export let name = "Default";
    export let status = "Default";

    const dispatch = createEventDispatcher();
    let skillPoint = 5;

    $: dispatch("skillPointChanged", skillPoint);

    function decrementSkillPoint() {
        if (skillPoint > 0) {
            skillPoint--;
        }
        dispatch("skillPointChanged", skillPoint);
    }

    function incrementSkillPoint() {
        skillPoint++;
        dispatch("skillPointChanged", skillPoint);
    }
</script>

<section>
    <h1>Welcome {name}</h1>
    <dl>
        <dt>Name</dt>
        <dd>{name}</dd>
        <dt>Status</dt>
        <dd>{status}</dd>
    </dl>

    <h2>Skill Point: {skillPoint}</h2>
    <button on:click={decrementSkillPoint}>-</button>
    <button on:click={incrementSkillPoint}>+</button>
</section>

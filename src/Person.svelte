<script>
    export let name = "Undefined name";
    export let age = 'Undefined age';
    export let job = 'Undefined job';
</script>
<style>
    div {
        border: 1px solid black;
        padding: 1rem;
        margin-bottom: 1rem;
    }
</style>
<main>
    <div>
        <p>Имя: <b>{name}</b></p>
        <p>Занятие: <b>{job}</b></p>
        {#if age < 18}
        <p>Пиво продавать нельзя</p>
        {:else}
        <p>Делай что хочешь</p>
        {/if}
    </div>
</main>
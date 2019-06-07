<script>
    export let name;
    export let points;
    
    const addPoints = () => points++
    const removePoints = () => points--
</script>

<div class="card mt-4">
    <div class="card-body">
        <h1>{name}</h1>
        <h3>
            <span>{points}</span>
            <button on:click={addPoints} class="btn btn-sm btn-primary">+</button>
            <button on:click={removePoints} class="btn btn-sm btn-danger">-</button>
        </h3>
    </div>
</div>
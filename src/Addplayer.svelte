<script>
    import { createEventDispatcher } from 'svelte'
    const dispatch = createEventDispatcher()

    let name = ''
    let points = 0

    const addPlayer = () => {
        dispatch('addplayer', { name, points })
        name = ''
        points = 0
    }
</script>

<div class="card mt-4">
    
    <div class="card-body">
        <div class="card-title">
            <h1>Add new player</h1>
        </div>

        <form on:submit|preventDefault={addPlayer}>
            <div class="form-group">
                <input type="text" placeholder="Enter name" class="form-control" bind:value={name}>
            </div>

            <div class="form-group">
                <input type="number" placeholder="Enter points" class="form-control" bind:value={points}>
            </div>

            <div class="form-group">
                <input type="submit" class="btn btn-primary" value="Add player">
            </div>
        </form>
    </div>
</div>
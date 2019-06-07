<script>
	import Header from './Header.svelte'
	import Player from './Player.svelte'
	import AddPlayer from './Addplayer.svelte'

	let players = [
		{
			name: 'Hai Dang',
			points: 40
		},
		{
			name: 'Huy Thien',
			points: 50
		},
		{
			name: 'Hoang Thach',
			points: 60
		}
	]

	const pushPlayer = e => {
		players = [e.detail, ...players]
	}
</script>

<Header />
<div class="container">
	<div class="col-md-6 offset-md-3">
		<AddPlayer on:addplayer={pushPlayer} />

		{#if players.length === 0}
			<p>There is no players</p>
		{:else}
			{#each players as player}
				<Player name={player.name} points={player.points} />
			{/each}
		{/if}
	</div>
</div>

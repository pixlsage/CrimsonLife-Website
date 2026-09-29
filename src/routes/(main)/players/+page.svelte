<script lang="ts">
    import PlayerCard from '$lib/components/playerCard.svelte';
    import playerData from '$lib/data/players.json';
</script>

<p style="text-align:center">
<strong>Click on the icons below to go to a player's page!</strong>
</p>

<p style="text-align:center">
    These pages are where each player's profiles are stored.<br>
    They include general info about the player as well as what they did in each series they were in.
</p>
<br>

<div class="playerGrid m-10">
    {#each playerData as player}
        <PlayerCard
            name={player.name}
            nickname={player.nickname}
            lives={player.lives}
            placement={player.placement}
            seasons={player.seasons}
            season={false}
        />
    {/each}
</div>
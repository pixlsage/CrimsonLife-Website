<script lang="ts">
    import PlayerCard from '$lib/components/playerCard.svelte';
	import TeamCard from '$lib/components/teamCard.svelte';
    import PlayerRef from '$lib/components/playerRef.svelte';
    import playerData from '$lib/data/players.json';
    import teamData from '$lib/data/TLteams.json';
    let showTeams = false;
    let showS1 = false;

    const seasonPlayers = playerData.filter(player =>
        player.seasonCheck.includes("CTL")
    );

    function getPlayer(name: string) {
        return playerData.find(p => p.name === name);
    };
</script>

<div style="margin: 1rem;">
    <div class="logo mb-5">
        <img src="/CTL-logo.png" class="series-logo" alt="third life logo">
    </div>
    <br>
    <div class="info" style="text-align:center">
    <h1 class="montserrat" style="text-align:center">INFO</h1>
    <h3 style="text-align:center">
    Start Date: 18 Oct 2026<br>End Date: N/A<br>Winner: N/A<br>
    </h3>
    </div>

    <br><h1 class="montserrat" style="text-align:center">PLAYERS</h1><br>
    <div class="playerGrid m-10">
        {#each seasonPlayers as player}
            <PlayerCard
                name={player.name}
                nickname={player.nickname}
                lives={player.lives}
                placement={player.placement}
                seasons={player.seasons}
                season={true}
            />
        {/each}
    </div>

    <br><h1 class="montserrat" style="text-align:center">TEAMS</h1><br>
    <div style="text-align: center"><button
        on:click={() => showTeams = !showTeams}
        aria-expanded={showTeams}
    > {showTeams ? "Hide Teams" : "Show Teams"}</button></div>
    {#if showTeams}
        <br>
        <div class="teams">
        {#each teamData as team}
            <TeamCard teamName={team.teamName}>
            {#each team.players as playerName}
                {#if getPlayer(playerName)}
                <PlayerCard {...getPlayer(playerName)} season={true}/>
                {:else}
                <p>Player not found: {playerName}</p>
                {/if}
            {/each}
            </TeamCard>
        {/each}
        </div>
    {/if}

    <br><h1 class="montserrat" style="text-align:center">GIMMICK</h1><br>
    <p style="text-align:center">The gimmick for this season has not yet been revealed!</p>

    <br><h1 class="montserrat" style="text-align:center">EVENTS</h1>
    <h2 class="montserrat" style="text-align:center">Session 1</h2>
    <div style="text-align: center"><button on:click={() => showS1 = !showS1} aria-expanded={showS1}> {showS1 ? "Hide S1 Summary" : "Show S1 Summary"}</button></div>
    {#if showS1}
        <div style="line-height: 1.8">
        <p style="text-align: center">
            <PlayerRef name="SxarI3tt" nickname="Scarlett" lives={3} season="thirdlife" /> steals the enchanting table from spawn<br>
            <PlayerRef name="Flamango37" lives={3} season="thirdlife"/> was shot by Pillager<br>
            <PlayerRef name="SaviMatteo2810" nickname="Savi" lives={3} season="thirdlife" />, <PlayerRef name="Sherbiscute" nickname="Rei" lives={3} season="thirdlife" /> and <PlayerRef name="SweetyYuso" nickname="Yuso" lives={3} season="thirdlife" /> form the <strong>Grase Kingdom</strong><br>
            <PlayerRef name="Genius_3" nickname="Genius" lives={3} season="thirdlife" /> and <PlayerRef name="SamStrange7" nickname="Sam" lives={3} season="thirdlife" /> form <strong>The Dutch</strong><br>
            <PlayerRef name="vc_spade" nickname="Spade" lives={3} season="thirdlife" /> and <PlayerRef name="ChampionofSpades" nickname="Misty" lives={3} season="thirdlife" /> form <strong>The Gold Diggers</strong><br>
            <PlayerRef name="ChampionofSpades" lives={3} season="thirdlife" /> fell from a high place<br>
            <PlayerRef name="Genius_3" nickname="Genius" lives={3} season="thirdlife" /> begins building <strong>The Dutch</strong>'s base<br>
            <PlayerRef name="typolar" lives={3} season="thirdlife" /> tried to swim in lava<br>
            <PlayerRef name="typolar" nickname="Polar" lives={2} season="thirdlife" /> begins building his base<br>
            <PlayerRef name="vc_spade" lives={3} season="thirdlife" /> fell from a high place<br>
            <PlayerRef name="PoochtheDog101" nickname="Pooch" lives={3} season="thirdlife" /> joins <strong>The Dutch</strong><br>
            <PlayerRef name="SxarI3tt" lives={3} season="thirdlife" /> fell from a high place<br>
            <PlayerRef name="Sherbiscute" nickname="Rei" lives={3} season="thirdlife" /> and <PlayerRef name="SweetyYuso" nickname="Yuso" lives={3} season="thirdlife" /> begin building the <strong>Grase Kingdom</strong>'s base<br>
            <PlayerRef name="CardinalVII" nickname="Card" lives={3} season="thirdlife" /> begins building <strong>Skynot</strong><br>
            <PlayerRef name="HubrisGekko" lives={3} season="thirdlife" /> burned to death<br>
            <PlayerRef name="HubrisGekko" nickname="Gekko" lives={2} season="thirdlife" /> begins building <strong>The Saloon</strong><br>
            <strong>The Dutch</strong> hire <PlayerRef name="ChampionofSpades" nickname="Misty" lives={2} season="thirdlife" /> to do work for them in exchange for gold<br>
            <PlayerRef name="pixlsage" nickname="Pix" lives={3} season="thirdlife" /> claims an area to build in<br>
            <PlayerRef name="HubrisGekko" nickname="Gekko" lives={2} season="thirdlife" /> and <PlayerRef name="Akamane55" nickname="Wes" lives={3} season="thirdlife" /> form <strong>The Cowboys</strong><br>
            <PlayerRef name="Manahhhh" nickname="Mana" lives={3} season="thirdlife" />, <PlayerRef name="Kibiyo_" nickname="Kibiyo" lives={3} season="thirdlife" /> and <PlayerRef name="Aerorolsa" nickname="Aero" lives={3} season="thirdlife" /> form <strong>The Hustlers</strong><br>
            <PlayerRef name="Manahhhh" nickname="Mana" lives={3} season="thirdlife" /> begins building <strong>The Hustlers</strong>' base<br>
            <PlayerRef name="FeebleBrush162" nickname="Ben" lives={3} season="thirdlife" /> and <PlayerRef name="CardinalVII" nickname="Card" lives={3} season="thirdlife" /> form the <strong>Skylanders</strong><br>
            <PlayerRef name="Akamane55" lives={3} season="thirdlife" /> was slain by <PlayerRef name="vc_spade" lives={2} season="thirdlife" /> ~ as revenge for killing its villagers<br>
            <PlayerRef name="typolar" nickname="Polar" lives={2} season="thirdlife" />, <PlayerRef name="Flamango37" nickname="Flamango" lives={2} season="thirdlife" /> and <PlayerRef name="Prosperity_" nickname="Prosperity" lives={3} season="thirdlife" /> form <strong>Polar's Polers</strong><br>
            <PlayerRef name="Stack_o_nhoj" nickname="John" lives={3} season="thirdlife" /> begins building <strong>The Carving Shack</strong><br>
            <PlayerRef name="pixlsage" nickname="Pix" lives={3} season="thirdlife" /> and <PlayerRef name="Genius_3" nickname="Genius" lives={3} season="thirdlife" /> hold a meeting for Genius' birthday and his announcement of the Farming Podcast<br>
        </p>
        </div>
    {/if}

    <br>
</div>

<style>
    .logo {
        width: 100%;
    }

    .series-logo {
        display: block;
        width: 256px;
        margin-left: auto;
        margin-right: auto;
    }
</style>
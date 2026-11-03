<script lang="ts">
    import PlayerCard from '$lib/components/playerCard.svelte';
	import TeamCard from '$lib/components/teamCard.svelte';
    import PlayerRef from '$lib/components/playerRef.svelte';
    import playerData from '$lib/data/players.json';
    import teamData from '$lib/data/TLteams.json';
    let showTeams = false;
    let showS1 = false;
    let showS2 = false;

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
    <a href="/seasons/thirdlife/lore">Lore Page</a><br>
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
                series="thirdlife"
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
                <PlayerCard {...getPlayer(playerName)} season={true} series="thirdlife"/>
                {:else}
                <p>Player not found: {playerName}</p>
                {/if}
            {/each}
            </TeamCard>
        {/each}
        </div>
    {/if}

    <br><h1 class="montserrat" style="text-align:center">GIMMICK</h1><br>
    <p style="text-align:center">This season's gimmick has been revealed, but only to a select few players.<br>
                                The only video that contains it is Card's Episode 2 - watch that if you want to know what it is!</p>

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
    <h2 class="montserrat" style="text-align:center">Session 2</h2>
    <div style="text-align: center"><button on:click={() => showS2 = !showS2} aria-expanded={showS2}> {showS2 ? "Hide S2 Summary" : "Show S2 Summary"}</button></div>
    {#if showS2}
        <div style="line-height: 1.8">
        <p style="text-align: center">
            The enchanting table is replaced at spawn due to <PlayerRef name="SxarI3tt" nickname="Scarlett" lives={2} season="thirdlife" />'s absence<br>
            <strong>The Dutch</strong>'s base is expanded<br>
            <PlayerRef name="PoochtheDog101" nickname="Pooch" lives={3} season="thirdlife" /> builds the <strong>Grounded Dutchman</strong><br>
            <PlayerRef name="pixlsage" nickname="Pix" lives={3} season="thirdlife" /> builds the <strong>Crimson Watchtower</strong><br>
            <PlayerRef name="vc_spade" nickname="Spade" lives={2} season="thirdlife" /> steals the enchanter from spawn<br>
            <PlayerRef name="PoochtheDog101" lives={3} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="Akamane55" nickname="Wes" lives={2} season="thirdlife" /> using a trap<br>
            <PlayerRef name="Manahhhh" nickname="Mana" lives={3} season="thirdlife" /> builds <strong>The Hustlers</strong>' base<br>
            <PlayerRef name="Genius_3" lives={3} season="thirdlife" /> tried to swim in lava ~ killed by <PlayerRef name="vc_spade" nickname="Spade" lives={2} season="thirdlife" /> using a trap<br>
            <PlayerRef name="Hobbbs" lives={3} season="thirdlife" /> drowned<br>
            <PlayerRef name="Aerorolsa" lives={3} season="thirdlife" /> fell from a high place ~ off the Crimson Watchtower<br>
            <PlayerRef name="Aerorolsa" lives={2} season="thirdlife" /> fell from a high place ~ failed a self-challenged bucket clutch off the Crimson Watchtower<br>
            Bets for the first red are collected by <strong>The Hustlers</strong> (nobody won)<br>
            <PlayerRef name="Genius_3" nickname="Genius" lives={2} season="thirdlife" /> records episode 1 of the Farming Podcast with <PlayerRef name="pixlsage" nickname="Pix" lives={3} season="thirdlife" /><br>
            <PlayerRef name="ChampionofSpades" lives={2} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="vc_spade" nickname="Spade" lives={2} season="thirdlife" /> using a minecart ride trap<br>
            <PlayerRef name="Hobbbs" lives={2} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="vc_spade" nickname="Spade" lives={2} season="thirdlife" /> using the same minecart trap<br>
            <PlayerRef name="Flamango37" nickname="Flamango" lives={2} season="thirdlife" /> begins building the glass dome around <strong>Polar's Polers</strong>' base<br>
            <PlayerRef name="CardinalVII" nickname="Card" lives={3} season="thirdlife" /> builds the wedding area<br>
            <PlayerRef name="Aerorolsa" nickname="Aero" lives={1} season="thirdlife" /> makes a trap at the wedding area<br>
            <PlayerRef name="Stack_o_nhoj" lives={3} season="thirdlife" /> was slain by <PlayerRef name="ChampionofSpades" lives={1} season="thirdlife" /><br>
            <PlayerRef name="vc_spade" lives={2} season="thirdlife" /> was impaled on a stalagmite while fighting <PlayerRef name="Akamane55" lives={2} season="thirdlife" /> ~ using <PlayerRef name="Aerorolsa" nickname="Aero" lives={1} season="thirdlife" />'s trap at the wedding area<br>
            <PlayerRef name="Akamane55" lives={2} season="thirdlife" /> was doomed to fall by <PlayerRef name="vc_spade" lives={1} season="thirdlife" /><br>
            <PlayerRef name="pixlsage" lives={3} season="thirdlife" /> was slain by <PlayerRef name="vc_spade" lives={1} season="thirdlife" /><br>
            <PlayerRef name="vc_spade" nickname="Spade" lives={2} season="thirdlife" /> gains a life and becomes yellow<br>
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
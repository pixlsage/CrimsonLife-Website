<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "HubrisGekko")
    import PlayerRef from '$lib/components/playerRef.svelte';
    import PlayerCard from '$lib/components/playerCard.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/7836332cfc49fe5e"> 
  <img src="/players/HubrisGekko.png" alt="Gekko" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat text-nickname">{player.nickname}</h2>
    <p>Username: {player.name}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: he/him</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: N/A</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat text-subtitle">Crimson Third Life</h2>
    <p>Placement: N/A<br>
    Team: The Cowboys</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Teamed up with <PlayerRef name="Akamane55" nickname="Wes" lives={3} season="thirdlife" /> - undecided team name</li>
      <li><strong>[S1]</strong> <PlayerRef name="HubrisGekko" lives={3} season="thirdlife" /> burned to death ~ in the bastion, after falling in lava</li>
      <li><strong>[S1]</strong> Built <strong>The Saloon</strong></li>
      <li><strong>[S1]</strong> Declined an offer from <PlayerRef name="CardinalVII" nickname="Card" lives={3} season="thirdlife" /> to join his team, then properly formed <strong>The Cowboys</strong> with <PlayerRef name="Akamane55" nickname="Wes" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Bet a diamond shovel on <PlayerRef name="Akamane55" nickname="Wes" lives={3} season="thirdlife" /> being the last green, but he died shortly after</li>
    </ul>
  </div>
</div>

<div>
  <br>
</div>

<style>
  .text-nickname {
    font-size: 2.5rem;
    margin-top: 0;
    margin-bottom: 0;
  }

  .text-subtitle {
    font-size: 2rem;
    margin-top: 0;
    margin-bottom: 0;
  }

  .season-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(0, 1fr));
    gap: 20px;
  }

  @media (max-width: 768px) {
    .season-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
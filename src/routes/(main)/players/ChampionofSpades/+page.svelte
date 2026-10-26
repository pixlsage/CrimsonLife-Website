<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "ChampionofSpades")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/a2ae60e245a52a41">
  <img src="/players/ChampionofSpades.png" alt="Misty" class="profile-img" />
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
    Team: The Gold Diggers</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed <strong>The Gold Diggers</strong> with <PlayerRef name="vc_spade" nickname="Spade" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> <PlayerRef name="ChampionofSpades" lives={3} season="thirdlife" /> fell from a high place</li>
      <li><strong>[S1]</strong> Did work for <strong>The Dutch</strong> in exchange for <PlayerRef name="PoochtheDog101" nickname="Pooch" lives={3} season="thirdlife" /> paying them 27 gold</li>
      <li><strong>[S1]</strong> Bet 5 gold on <PlayerRef name="Flamango37" nickname="Flamango" lives={2} season="thirdlife" /> being the first red</li>
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
<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "flamango")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/59a6e119b30bc671">
  <img src="/players/{player.name}.png" alt="{player.name}" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat player-text-name">{player.name.toUpperCase()}</h2>
    <p>Username: {player.username}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: he/him</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: N/A</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat player-text-subtitle" style="text-align: center">Other Skins</h2>
<div class="skin-list">
  <figure class="skin">
    <a href="https://namemc.com/skin/d6a2284ba6b388c8">
    <img src="/players/thirdlife/flamango.png" alt="third life skin"></a>
    <figcaption style="margin-top: 0.5rem">Third Life</figcaption>
  </figure>
</div>
<br>
<br>
<h2 class="montserrat player-text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat player-text-subtitle">Crimson Third Life</h2>
    <p>Placement: N/A<br>
    Team: Polar's Polers</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> <PlayerRef name="Flamango" username="Flamango37" lives={3} season="thirdlife" /> was shot by Pillager</li>
      <li><strong>[S1]</strong> Explored the ancient city while caving, and the bastion in the Nether</li>
      <li><strong>[S1]</strong> Bet 18 gold on <PlayerRef name="Misty" lives={2} season="thirdlife" /> being the first red</li>
      <li><strong>[S1]</strong> Formed <strong> Polar's Polers</strong> with <PlayerRef name="Polar" lives={2} season="thirdlife" /> and <PlayerRef name="Prosperity" lives={3} season="thirdlife" /></li>
      <li><strong>[S2]</strong> Started building the glass dome around <strong>Polar's Polers</strong>' base</li>
    </ul>
  </div>
</div>

<div>
  <br>
</div>

<style>
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
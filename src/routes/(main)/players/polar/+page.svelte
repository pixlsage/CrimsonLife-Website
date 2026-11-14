<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "polar")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/36c35f7c58cde123">
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
    <a href="https://namemc.com/skin/c94e734e63e43309">
    <img src="/players/thirdlife/polar.png" alt="third life skin"></a>
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
      <li><strong>[S1]</strong> <PlayerRef name="Polar" username="typolar" lives={3} season="thirdlife" /> tried to swim in lava</li>
      <li><strong>[S1]</strong> Started building his base on the snowy mountain</li>
      <li><strong>[S1]</strong> Became allies with <PlayerRef name="Savi" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Formed <strong>Polar's Polers</strong> with <PlayerRef name="Flamango" lives={2} season="thirdlife" /> and <PlayerRef name="Prosperity" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Gave <PlayerRef name="Sam" lives={3} season="thirdlife" /> a potato in exchange for a diamond</li>
      <li><strong>[S3]</strong> Assisted in trapping <strong>Skynot</strong> using blue glass panes</li>
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
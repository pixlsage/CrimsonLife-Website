<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "savi")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/9d6b55bac914b52d">
  <img src="/players/{player.name}.png" alt="{player.name}" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat player-text-name">{player.name.toUpperCase()}</h2>
    <p>Username: {player.username}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: any/all</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: N/A</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat player-text-subtitle" style="text-align: center">Other Skins</h2>
<div class="skin-list">
  <figure class="skin">
    <a href="https://namemc.com/skin/9957b40e6dc7b8bf">
    <img src="/players/thirdlife/savi.png" alt="third life skin"></a>
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
    Team: Grase Kingdom</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed the <strong>Grase Kingdom</strong> with <PlayerRef name="Rei" lives={3} season="thirdlife" /> and <PlayerRef name="Yuso" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Became allies with <PlayerRef name="Polar" lives={2} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Found a chicken with the aim of bringing it to their team's base, but it died before making it</li>
      <li><strong>[S3]</strong> <PlayerRef name="Savi" username="SaviMatteo2810" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Scarlett" username="SxarI3tt" lives={1} season="thirdlife" /></li>
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
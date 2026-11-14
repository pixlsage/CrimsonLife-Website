<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "rei")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/04ab7ccdb3024764">
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
<h2 class="montserrat player-text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat player-text-subtitle">Crimson Third Life</h2>
    <p>Placement: N/A<br>
    Team: Grase Kingdom</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed the <strong>Grase Kingdom</strong> with <PlayerRef name="Savi" lives={3} season="thirdlife" /> and <PlayerRef name="Yuso" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Found villagers and looked for somewhere to build a base</li>
      <li><strong>[S1]</strong> Started building the <strong>Grase Kingdom</strong>'s base with <PlayerRef name="Yuso" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Recorded Episode 2 of the Farming Podcast with <PlayerRef name="Genius" lives={1} season="thirdlife" /></li>
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
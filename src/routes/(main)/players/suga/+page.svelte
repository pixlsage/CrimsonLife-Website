<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "suga")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/e0613b211c320e8b">
  <img src="/players/{player.name}.png" alt="{player.name}" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat player-text-name">{player.name.toUpperCase()}</h2>
    <p>Username: {player.username}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: she/they</p>
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
    Team: Unnamed Team</p>
    <ul class="bullet-list">
      <li><strong>[S3]</strong> Formed the <strong>Unnamed Team</strong> with <PlayerRef name="Aquorn" lives={3} season="thirdlife" /> and <PlayerRef name="Scarlett" lives={2} season="thirdlife" /></li>
      <li><strong>[S3]</strong> <PlayerRef name="Suga" username="chaotic_Suga" lives={3} season="thirdlife" /> fell from a high place</li>
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
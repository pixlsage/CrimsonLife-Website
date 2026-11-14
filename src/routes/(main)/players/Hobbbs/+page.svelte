<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "hobbbs")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/9d2b9fa625df49ca">
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
    <a href="https://namemc.com/skin/b8cb5cbe419ce074">
    <img src="/players/thirdlife/hobbbs.png" alt="third life skin"></a>
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
    Team: Unaligned</p>
    <ul class="bullet-list">
      <li><strong>[S2]</strong> <PlayerRef name="Hobbbs" lives={3} season="thirdlife" /> drowned</li>
      <li><strong>[S2]</strong> <PlayerRef name="Hobbbs" lives={2} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="Spade" lives={2} season="thirdlife" /> using a minecart ride trap</li>
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
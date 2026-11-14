<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "john")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/a8f2e4e66c557416">
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
    <a href="https://namemc.com/skin/e724896dd9ab3591">
    <img src="/players/thirdlife/john.png" alt="third life skin"></a>
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
      <li><strong>[S1]</strong> Built the <strong>Carving Shack</strong></li>
      <li><strong>[S1]</strong> Gave other members jack-o-lanterns</li>
      <li><strong>[S2]</strong> <PlayerRef name="John" username="Stack_o_nhoj" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Misty" username="ChampionofSpades" lives={1} season="thirdlife" /></li>
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
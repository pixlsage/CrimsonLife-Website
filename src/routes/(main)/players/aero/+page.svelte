<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "aero")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/764b4d24d06828bc">
  <img src="/players/{player.name}.png" alt="{player.name}" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat player-text-name">{player.name.toUpperCase()}</h2>
    <p>Username: {player.username}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: she/he</p>
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
    Team: The Hustlers</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed <strong>The Hustlers</strong> with <PlayerRef name="Mana" lives={3} season="thirdlife" /> and <PlayerRef name="Kibiyo" lives={3} season="thirdlife" /></li>
      <li><strong>[S2]</strong> <PlayerRef name="Aero" username="Aerorolsa" lives={3} season="thirdlife" /> fell from a high place ~ off the Crimson Watchtower</li>
      <li><strong>[S2]</strong> <PlayerRef name="Aero" username="Aerorolsa" lives={2} season="thirdlife" /> fell from a high place ~ failed self-challenged bucket clutch off the Crimson Watchtower</li>
      <li><strong>[S2]</strong> Made a trap at the wedding area, which is used by <PlayerRef name="Wes" lives={2} season="thirdlife" /> to kill <PlayerRef name="Spade" lives={2} season="thirdlife" /></li>
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
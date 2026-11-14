<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "mana")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/c383900590e368dc">
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
    Team: The Hustlers</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Looted the bastion in the Nether after caving</li>
      <li><strong>[S1]</strong> Formed <strong>The Hustlers</strong> with <PlayerRef name="Kibiyo" lives={3} season="thirdlife" /> and <PlayerRef name="Aero" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Started building <strong>The Hustlers</strong>' base</li>
      <li><strong>[S2]</strong> Collected bets for the first red, as nobody won</li>
      <li><strong>[S3]</strong> Gambled with <PlayerRef name="Sam" lives={3} season="thirdlife" /> to keep <PlayerRef name="Genius" lives={1} season="thirdlife" />'s soul, and lost</li>
      <li><strong>[S3]</strong> <PlayerRef name="Mana" username="Manahhhh" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Wes" username="Akamane55" lives={1} season="thirdlife" /> ~ with help from <PlayerRef name="Scarlett" lives={1} season="thirdlife" /></li>
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
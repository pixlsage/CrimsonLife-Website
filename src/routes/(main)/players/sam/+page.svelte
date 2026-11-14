<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "sam")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/c9ecf443184f5cf3">
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
    Team: The Dutch</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed <strong>The Dutch</strong> with <PlayerRef name="Genius" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Invited <PlayerRef name="Pooch" lives={3} season="thirdlife" /> to join <strong>The Dutch</strong> after caving</li>
      <li><strong>[S1]</strong> Gave a diamond to <PlayerRef name="Polar" lives={2} season="thirdlife" /> in exchange for a potato</li>
      <li><strong>[S3]</strong> Became allies with <PlayerRef name="Pix" lives={2} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Gambled with <PlayerRef name="Mana" lives={3} season="thirdlife" /> to get <PlayerRef name="Genius" lives={1} season="thirdlife" />'s soul back, and won</li>
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
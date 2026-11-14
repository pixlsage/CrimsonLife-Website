<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "pix")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/b17bce084f05d51b">
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
<h2 class="montserrat player-text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat player-text-subtitle">Crimson Third Life</h2>
    <p>Placement: N/A<br>
    Team: Unaligned</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Found a spot on the cherry mountain to build on, but no structure was made</li>
      <li><strong>[S1]</strong> Went to the Nether and harvested the only crimson tree</li>
      <li><strong>[S1]</strong> Met up with <PlayerRef name="Genius" lives={3} season="thirdlife" /> to do the birthday meeting</li>
      <li><strong>[S2]</strong> Built the <strong>Crimson Watchtower</strong></li>
      <li><strong>[S2]</strong> Recorded Episode 1 of the Farming Podcast with <PlayerRef name="Genius" lives={2} season="thirdlife" /></li>
      <li><strong>[S2]</strong> <PlayerRef name="Pix" username="pixlsage" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Spade" username="vc_spade" lives={1} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Offered by <PlayerRef name="Pooch" lives={2} season="thirdlife" /> to join <strong>The Dutch</strong>, but declined</li>
      <li><strong>[S3]</strong> Became allies with <PlayerRef name="Sam" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Rebuilt the recording studio with <PlayerRef name="Genius" lives={1} season="thirdlife" /></li>
      <li><strong>[S3]</strong> <PlayerRef name="Pix" username="pixlsage" lives={2} season="thirdlife" /> tried to swim in lava</li>
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
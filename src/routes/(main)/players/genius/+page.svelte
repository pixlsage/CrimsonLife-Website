<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "genius")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/6e67142b660354a2">
  <img src="/players/{player.name}.png" alt="{player.name}" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat player-text-name">{player.name.toUpperCase()}</h2>
    <p>Username: {player.username}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: he/they</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: N/A</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat player-text-subtitle" style="text-align: center">Other Skins</h2>
<div class="skin-list">
  <figure class="skin">
    <a href="https://namemc.com/skin/2404934aaa293a5e">
    <img src="/players/thirdlife/genius.png" alt="third life skin"></a>
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
    Team: The Dutch</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed <strong>The Dutch</strong> with <PlayerRef name="Sam" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Started building <strong>The Dutch</strong>'s base</li>
      <li><strong>[S1]</strong> Recruited <PlayerRef name="Pooch" lives={3} season="thirdlife" /> to his team</li>
      <li><strong>[S1]</strong> Met up with <PlayerRef name="Pix" lives={3} season="thirdlife" /> to do the birthday meeting</li>
      <li><strong>[S2]</strong> Expanded <strong>The Dutch</strong>'s base</li>
      <li><strong>[S2]</strong> <PlayerRef name="Genius" username="Genius_3" lives={3} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="Wes" lives={2} season="thirdlife" /> using a trap</li>
      <li><strong>[S2]</strong> Recorded Episode 1 of the Farming Podcast with <PlayerRef name="Pix" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> <PlayerRef name="Genius" username="Genius_3" lives={2} season="thirdlife" /> tried to swim in lava ~ killed by <PlayerRef name="Wes" lives={1} season="thirdlife" /> using the same trap</li>
      <li><strong>[S3]</strong> Rebuilt the recording studio with <PlayerRef name="Pix" lives={2} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Recorded Episode 2 of the Farming Podcast with <PlayerRef name="Rei" lives={3} season="thirdlife" /> and <PlayerRef name="Gekko" lives={2} season="thirdlife" /></li>
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
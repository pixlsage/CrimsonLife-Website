<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "pixlsage")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/b17bce084f05d51b">
  <img src="/players/pixlsage.png" alt="Pix" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat text-nickname">{player.nickname}</h2>
    <p>Username: {player.name}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: any/all</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: N/A</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat text-subtitle" style="text-align: center">Other Skins</h2>
<div class="skin-list">
  <figure class="skin">
    <a href="https://namemc.com/skin/b17bce084f05d51b">
    <img src="/players/pixlsage.png" alt="third life skin"></a>
    <figcaption style="margin-top: 0.5rem">Third Life</figcaption>
  </figure>
</div>
<br>
<br>
<h2 class="montserrat text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat text-subtitle">Crimson Third Life</h2>
    <p>Placement: N/A<br>
    Team: Unaligned</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Found a spot on the cherry mountain to build on, but no structure was made</li>
      <li><strong>[S1]</strong> Went to the Nether and harvested the only crimson tree</li>
      <li><strong>[S1]</strong> Met up with <PlayerRef name="Genius_3" nickname="Genius" lives={3} season="thirdlife" /> to do the birthday meeting</li>
    </ul>
  </div>
</div>

<div>
  <br>
</div>

<style>
  .text-nickname {
    font-size: 2.5rem;
    margin-top: 0;
    margin-bottom: 0;
  }

  .text-subtitle {
    font-size: 2rem;
    margin-top: 0;
    margin-bottom: 0;
  }

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
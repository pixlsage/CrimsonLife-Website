<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "pooch")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/58e7e3272ccd9267">
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
    <a href="https://namemc.com/skin/b974303240d0c052">
    <img src="/players/thirdlife/pooch.png" alt="third life skin"></a>
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
      <li><strong>[S1]</strong> Joined <strong>The Dutch</strong> with <PlayerRef name="Genius" lives={3} season="thirdlife" /> and <PlayerRef name="Sam" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Gave <PlayerRef name="Misty" lives={2} season="thirdlife" /> 27 gold in exchange for him doing work for <strong>The Dutch</strong></li>
      <li><strong>[S2]</strong> Built the <strong>Grounded Dutchman</strong></li>
      <li><strong>[S2]</strong> <PlayerRef name="Pooch" username="PoochtheDog101" lives={3} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="Wes" lives={2} season="thirdlife" /> using a trap</li>
      <li><strong>[S3]</strong> Officiated the wedding between <PlayerRef name="Prosperity" lives={3} season="thirdlife" /> and <PlayerRef name="Card" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Tries to get <PlayerRef name="Pix" lives={2} season="thirdlife" /> to join his team, but fails</li>
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
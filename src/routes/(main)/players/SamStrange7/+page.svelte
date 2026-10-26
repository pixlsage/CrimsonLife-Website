<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "SamStrange7")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/c9ecf443184f5cf3">
  <img src="/players/SamStrange7.png" alt="Sam" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat text-nickname">{player.nickname}</h2>
    <p>Username: {player.name}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: he/him</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: N/A</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat text-subtitle">Crimson Third Life</h2>
    <p>Placement: N/A<br>
    Team: The Dutch</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed <strong>The Dutch</strong> with <PlayerRef name="Genius_3" nickname="Genius" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Invited <PlayerRef name="PoochtheDog101" nickname="Pooch" lives={3} season="thirdlife" /> to join <strong>The Dutch</strong> after caving</li>
      <li><strong>[S1]</strong> Gave a diamond to <PlayerRef name="typolar" nickname="Polar" lives={2} season="thirdlife" /> in exchange for a potato</li>
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
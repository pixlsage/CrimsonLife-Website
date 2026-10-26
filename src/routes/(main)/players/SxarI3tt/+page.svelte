<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "SxarI3tt")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/74f3635a97821743">
  <img src="/players/SxarI3tt.png" alt="Scarlett" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat text-nickname">{player.nickname}</h2>
    <p>Username: {player.name}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: she/they</p>
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
    Team: None</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Stole the enchanter from spawn</li>
      <li><strong>[S1]</strong> <PlayerRef name="SxarI3tt" lives={3} season="thirdlife" /> fell from a high place</li>
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
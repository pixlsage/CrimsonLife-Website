<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "card")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/3735c4ba74e3dfe8">
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
    Team: Skylanders</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Started building <strong>Skynot</strong></li>
      <li><strong>[S1]</strong> Invited <PlayerRef name="Gekko" lives={2} season="thirdlife" /> and <PlayerRef name="Wes" lives={3} season="thirdlife" /> to join, but they declined</li>
      <li><strong>[S1]</strong> Formed the <strong>Skylanders</strong> with <PlayerRef name="Ben" lives={3} season="thirdlife" /></li>
      <li><strong>[S2]</strong> Built the wedding area</li>
      <li><strong>[S3]</strong> Had a wedding with <PlayerRef name="Prosperity" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Became allies with <PlayerRef name="Aquorn" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> <PlayerRef name="Spade" username="vc_spade" lives={1} season="thirdlife" /> drowned while trying to fight <PlayerRef name="Card" username="CardinalVII" lives={3} season="thirdlife" /></li>
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
<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "vc_spade")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/a73a385104693a56">
  <img src="/players/vc_spade.png" alt="Spade" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat text-nickname">{player.nickname}</h2>
    <p>Username: {player.name}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: it/its</p>
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
    Team: The Gold Diggers</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Found villagers and hid them away</li>
      <li><strong>[S1]</strong> Formed <strong>The Gold Diggers</strong> with <PlayerRef name="ChampionofSpades" nickname="Misty" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> <PlayerRef name="vc_spade" lives={3} season="thirdlife" /> fell from a high place</li>
      <li><strong>[S1]</strong> Disovered the villagers had been killed, looked for who had done it</li>
      <li><strong>[S1]</strong> <PlayerRef name="Akamane55" lives={3} season="thirdlife" /> was slain by <PlayerRef name="vc_spade" lives={2} season="thirdlife" /> ~ as revenge for killing the villagers</li>
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
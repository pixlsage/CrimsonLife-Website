<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "spade")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/a73a385104693a56">
  <img src="/players/{player.name}.png" alt="{player.name}" class="profile-img" />
  </a>

  <div class="profile-info">
    <h2 class="montserrat player-text-name">{player.name.toUpperCase()}</h2>
    <p>Username: {player.username}</p>
    <p>Former Name(s): None</p>
    <p>Pronouns: it/its</p>
    <p>Season(s): {player.seasonCheck.join(", ")}</p>
    <p>Average Placement: 24th</p>
  </div>
</div>
<br>
<br>
<h2 class="montserrat player-text-subtitle" style="text-align: center">Seasons</h2>
<div class="season-grid">
  <div class="season-info">
    <h2 class="montserrat player-text-subtitle">Crimson Third Life</h2>
    <p>Placement: 24th<br>
    Team: The Gold Diggers</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Found villagers and hid them away</li>
      <li><strong>[S1]</strong> Formed <strong>The Gold Diggers</strong> with <PlayerRef name="Misty" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> <PlayerRef name="Spade" username="vc_spade" lives={3} season="thirdlife" /> fell from a high place</li>
      <li><strong>[S1]</strong> Disovered the villagers had been killed, looked for who had done it</li>
      <li><strong>[S1]</strong> <PlayerRef name="Wes" username="Akamane55" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Spade" username="vc_spade" lives={2} season="thirdlife" /> ~ as revenge for killing the villagers</li>
      <li><strong>[S2]</strong> <PlayerRef name="Genius" username="Genius_3" lives={3} season="thirdlife" /> tried to swim in lava ~ because of a trap it made</li>
      <li><strong>[S2]</strong> <PlayerRef name="Misty" username="ChampionofSpades" lives={2} season="thirdlife" /> fell from a high place ~ because of a minecart ride trap it used</li>
      <li><strong>[S2]</strong> <PlayerRef name="Hobbbs" lives={2} season="thirdlife" /> fell from a high place ~ because of the same minecart trap</li>
      <li><strong>[S2]</strong> <PlayerRef name="Spade" username="vc_spade" lives={2} season="thirdlife" /> was impaled on a stalagmite while trying to escape <PlayerRef name="Wes" username="Akamane55" lives={2} season="thirdlife" /> ~ using a trap <PlayerRef name="Aerorolsa" nickname="Aero" lives={1} season="thirdlife" /> made</li>
      <li><strong>[S2]</strong> <PlayerRef name="Wes" username="Akamane55" lives={2} season="thirdlife" /> was doomed to fall by <PlayerRef name="Spade" username="vc_spade" lives={1} season="thirdlife" /></li>
      <li><strong>[S2]</strong> <PlayerRef name="Pix" username="pixlsage" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Spade" username="vc_spade" lives={1} season="thirdlife" /></li>
      <li><strong>[S2]</strong> Gained a life to become yellow</li>
      <li><strong>[S3]</strong> <PlayerRef name="Spade" username="vc_spade" lives={2} season="thirdlife" /> fell from a high place</li>
      <li><strong>[S3]</strong> <PlayerRef name="Spade" username="vc_spade" lives={1} season="thirdlife" /> drowned while trying to fight <PlayerRef name="Card" username="CardinalVII" lives={3} season="thirdlife" /></li>
      <li><strong>[S3]</strong> <PlayerRef name="Spade" lives={0} season="thirdlife" /> is eliminated in 24th place</li>
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
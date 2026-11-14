<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "misty")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/a2ae60e245a52a41">
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
    Team: The Gold Diggers, The Cowboys</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Formed <strong>The Gold Diggers</strong> with <PlayerRef name="Spade" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> <PlayerRef name="Misty" username="ChampionofSpades" lives={3} season="thirdlife" /> fell from a high place</li>
      <li><strong>[S1]</strong> Did work for <strong>The Dutch</strong> in exchange for <PlayerRef name="Pooch" lives={3} season="thirdlife" /> paying them 27 gold</li>
      <li><strong>[S1]</strong> Bet 5 gold on <PlayerRef name="Flamango" lives={2} season="thirdlife" /> being the first red</li>
      <li><strong>[S2]</strong> <PlayerRef name="Misty" username="ChampionofSpades" lives={2} season="thirdlife" /> fell from a high place ~ killed by <PlayerRef name="Spade" lives={2} season="thirdlife" /> using a minecart ride trap</li>
      <li><strong>[S2]</strong> <PlayerRef name="John" username="Stack_o_nhoj" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Misty" username="ChampionofSpades" lives={1} season="thirdlife" /></li>
      <li><strong>[S3]</strong> <PlayerRef name="Ben" username="FeebleBrush162" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Misty" username="ChampionofSpades" lives={1} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Gained a life to become yellow</li>
      <li><strong>[S3]</strong> Joined <strong>The Cowboys</strong> after <PlayerRef name="Spade" lives={0} season="thirdlife" />'s death</li>
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
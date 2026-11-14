<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "gekko")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/7836332cfc49fe5e"> 
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
    Team: The Cowboys</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Teamed up with <PlayerRef name="Wes" lives={3} season="thirdlife" /> - undecided team name</li>
      <li><strong>[S1]</strong> <PlayerRef name="Gekko" username="HubrisGekko" lives={3} season="thirdlife" /> burned to death ~ in the bastion, after falling in lava</li>
      <li><strong>[S1]</strong> Built <strong>The Saloon</strong></li>
      <li><strong>[S1]</strong> Declined an offer from <PlayerRef name="Card" lives={3} season="thirdlife" /> to join his team, then properly formed <strong>The Cowboys</strong> with <PlayerRef name="Wes" lives={3} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Bet a diamond shovel on <PlayerRef name="Wes" lives={3} season="thirdlife" /> being the last green, but he died shortly after</li>
      <li><strong>[S3]</strong> Assisted in trapping <strong>Skynot</strong> using blue glass panes</li>
      <li><strong>[S3]</strong> Recorded Episode 2 of the Farming Podcast with <PlayerRef name="Genius" lives={1} season="thirdlife" /></li>
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
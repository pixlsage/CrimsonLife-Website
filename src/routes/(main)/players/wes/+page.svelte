<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "wes")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/c6e49cb64670e31a">
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
      <li><strong>[S1]</strong> Teamed up with <PlayerRef name="Gekko" lives={3} season="thirdlife" /> - undecided team name</li>
      <li><strong>[S1]</strong> Caved and searched a bastion, then properly formed <strong>The Cowboys</strong> with <PlayerRef name="Gekko" lives={2} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Killed <PlayerRef name="Spade" lives={2} season="thirdlife" />'s villagers</li>
      <li><strong>[S1]</strong> <PlayerRef name="Wes" username="Akamane55" lives={3} season="thirdlife" /> was slain by <PlayerRef name="Spade" username="vc_spade" lives={2} season="thirdlife" /> ~ as revenge for killing the villagers</li>
      <li><strong>[S2]</strong> <PlayerRef name="Pooch" username="PoochtheDog101" lives={3} season="thirdlife" /> fell from a high place ~ because of a trap he made</li>
      <li><strong>[S2]</strong> <PlayerRef name="Spade" username="vc_spade" lives={2} season="thirdlife" /> was impaled on a stalagmite while trying to escape <PlayerRef name="Wes" username="Akamane55" lives={2} season="thirdlife" /> ~ using a trap <PlayerRef name="Aerorolsa" nickname="Aero" lives={1} season="thirdlife" /> made</li>
      <li><strong>[S2]</strong> <PlayerRef name="Wes" username="Akamane55" lives={2} season="thirdlife" /> was doomed to fall by <PlayerRef name="Spade" username="vc_spade" lives={1} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Recruited <PlayerRef name="Misty" lives={2} season="thirdlife" /> into <strong>The Cowboys</strong></li>
      <li><strong>[S3]</strong> Trapped <strong>Skynot</strong> using blue glass panes, with help from <PlayerRef name="Gekko" lives={2} season="thirdlife" /> and <PlayerRef name="Polar" lives={2} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Used <span class="sense">SENSE</span>, but doesn't get a kill</li>
      <li><strong>[S3]</strong> <PlayerRef name="Mana" username="Manahhhh" lives={3} season="thirdlife" /> is slain by <PlayerRef name="Wes" username="Akamane55" lives={1} season="thirdlife" /> - with help from <PlayerRef name="Scarlett" lives={1} season="thirdlife" /></li>
      <li><strong>[S3]</strong> Gained a life to become yellow</li>
      <li><strong>[S3]</strong> <PlayerRef name="Wes" username="Akamane55" lives={2} season="thirdlife" /> fell from a high place</li>
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
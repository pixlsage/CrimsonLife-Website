<script lang="ts">
    import playerData from '$lib/data/players.json';
    const player = playerData.find(p => p.name === "Akamane55")
    import PlayerRef from '$lib/components/playerRef.svelte';
</script>

<div class="player-profile">

  <a href="https://namemc.com/skin/c6e49cb64670e31a">
  <img src="/players/Akamane55.png" alt="Wes" class="profile-img" />
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
    Team: The Cowboys</p>
    <ul class="bullet-list">
      <li><strong>[S1]</strong> Teamed up with <PlayerRef name="HubrisGekko" nickname="Gekko" lives={3} season="thirdlife" /> - undecided team name</li>
      <li><strong>[S1]</strong> Caved and searched a bastion, then properly formed <strong>The Cowboys</strong> with <PlayerRef name="HubrisGekko" nickname="Gekko" lives={2} season="thirdlife" /></li>
      <li><strong>[S1]</strong> Killed <PlayerRef name="vc_spade" nickname="Spade" lives={2} season="thirdlife" />'s villagers</li>
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
<script>
    export var name = "";
    export var nickname = "";
    export var lives = 3;
    export var season = "";
    let imageAttempt = 0;

    function getPlayerColour(lives) {
        if (lives >= 4) {
            return "darkGreenLife"
        } else if (lives === 3) {
            return "greenLife"
        } else if (lives === 2) {
            return "yellowLife"
        } else if (lives == 1) {
            return "redLife"
        } else {
            return "noLives"
        }
    }

    function handleImageError(e) {
        const img = e.currentTarget;

        imageAttempt += 1;

        if (imageAttempt === 1) {
            img.src = `/players/${name}.png`;
        } else if (imageAttempt === 2) {
            img.src = `/players/placeholder.png`;
        }
    }
</script>

<a href={`/players/${name}`}>
    <span class="player-ref">
        <img
            src={`/players/${season}/${name}.png`}
            on:error={handleImageError}
            alt={name}
            class="player-icon"
        />
        <span class={getPlayerColour(lives)}>{nickname || name}</span>
    </span>
</a>

<style>
    .player-ref {
        display: inline-flex;
        align-items: center;
        gap: 0.2rem;
        vertical-align: -0.35rem;
        line-height: 1;
    }

    .player-icon {
        display: block;
        width: 1.4em;
        height: 1.4em;
        object-fit: contain;
    }
</style>
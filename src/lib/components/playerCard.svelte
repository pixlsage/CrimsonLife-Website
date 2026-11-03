<script>
    export var name = "";
    export var nickname = "";
    export var lives = 3;
    export var placement = "";
    export var seasons = "";
    export var season = false;
    export var series = "";
    let imageAttempt = 0;

    /**
	 * @param {number} lives
	 */
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
<a href="/players/{name}">
    <div class={"PlayerCard"}>
        <img
            src={`/players/${series}/${name}.png`}
            on:error={handleImageError}
            class={`h-36 mx-auto mt-5 mb-10 drop-shadow-[0_35px_35px_rgba(0,0,0,0.6)] ${season ? getPlayerColour(lives) : ""}`}
            width="150"
            alt={nickname}/>
        <h2 class={`montserrat ${season ? getPlayerColour(lives) : ""}`}>
        <strong>{nickname}</strong>
        </h2>
        <p style="color:white">{name}</p>
        {#if season}
            <p style="color:white">{placement}</p>
        {/if}
        <p style="color:white">{seasons}</p>
    </div>
</a>

<style>
    h2 {
        margin-bottom: 3px
    }
    p {
        margin: 0
    }
</style>
<script>
    export var teamName = "";
    export var notes = "";
</script>

<div class="teamCard">
    <h2 class="montserrat text-gray-200 text-title" style="text-align: center">{teamName}</h2>
    <div class="teamGrid">
        <slot></slot>
    </div>
    <p style="text-align: center">{notes}</p>
</div>

<style>
    .teamCard {
        max-width: 1600px;
        width: calc(100% - 2rem);
        margin: 0 auto 2rem;
        padding: 1rem;
        border-radius: 1rem;
        background-color: var(--secondary);
        box-shadow: 0 0 30px rgba(70, 0, 34, 0.3);
    }

    .text-title {
        font-size: 2rem;
        margin-top: 0;
    }
</style>

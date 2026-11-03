<script>
    let displayedText = $state('');
    let isTyping = $state(false);
    let typedText = '';
    let started = false;

    const chars = 'ABCDEFGHKMNOPQRSTUVWXYZ23456789';

    const block =
        `[_____] are a group of cosmic entities, remnants of [________], desperate for attention after centuries of drifting through obscurity.
        But very recently, they [_________]. Their interaction with mortals strengthens them, so they keep them around - [_____________] in order to make things go their way.
        It almost seems as if [_____________].

        There are others like them, but there's no point in cooperating. They operate differently.
        [_______________________].
        [__________], even if others might "discourage" it. Others may say their antics are an "interference with the narrative", but [___________]… and so they're feared.

        [_______________], allowing them to influence narratives through their inherent thirst for chaos.
        It seems they have a motive for [__________], and it can only be assumed that the more this happens, the closer they become to their goal...
        ...whatever it is.

        This is the first world they've gotten a real hold on, and [_____________].
        They're using the players as a medium to stay in control, so [___________]...`;

    function randomChar() {
        return chars[Math.floor(Math.random() * chars.length)];
    }

    function scramble(text) {
        let insidePlaceholder = false;

        return text
            .split('')
            .map(char => {
                if (char === '[') {
                    insidePlaceholder = true;
                    return char;
                }
                if (char === ']') {
                    insidePlaceholder = false;
                    return char;
                }
                if (insidePlaceholder && char === '_') {
                    return randomChar();
                }
                return char;
            })
            .join('');
    }

    async function typeText(text) {
        isTyping = true;

        for (let i = 0; i < text.length; i++) {
            typedText += text[i];
            await new Promise(resolve => setTimeout(resolve, 40));
        }

        isTyping = false;
    }

    $effect(() => {
        if (started) return;
        started = true;

        typeText(block);

        const interval = setInterval(() => {
            displayedText = scramble(typedText);
        }, 50);

        return () => clearInterval(interval);
    });
</script>

<div class="text-block">
    <div class="text-container">
        <h3 class="montserrat" style="text-align:center">Stage 1</h3>
        <p>{displayedText}</p>
        <br>
    </div>
</div>

<style>
    .text-block {
        max-width: 600px;
        margin: 75px auto;
        text-align: center;
    }

    .text-container {
        min-height: 400px;
        white-space: pre-line;
        font-family: 'Minecraft-Regular', sans-serif;
    }
</style>
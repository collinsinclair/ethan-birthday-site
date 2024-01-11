<script>
    import {onMount} from 'svelte';

    function typewriter(element, text, delay = 100) {
        return new Promise((resolve, reject) => {
            const interval = setInterval(() => {
                if (text.length > 0) {
                    element.innerHTML += text.shift();
                } else {
                    clearInterval(interval);
                    resolve();
                }
            }, delay);
        });
    }

    onMount(async () => {
        const title = document.getElementById('title');
        const titleText = 'Ethan Pierce';
        await typewriter(title, titleText.split(''));

        const line1 = document.getElementById('line1');
        const line1Text = 'We understand it is your birthday.';
        await typewriter(line1, line1Text.split(''));

        const line2 = document.getElementById('line2');
        const line2Text = 'Happy birthday.';
        await typewriter(line2, line2Text.split(''));

        const line3 = document.getElementById('line3');
        const line3Text = 'As a reminder, you may NOT celebrate on company time.';
        await typewriter(line3, line3Text.split(''));

        const line4 = document.getElementById('line4');
        const line4Text = 'Now get back to work.';
        await typewriter(line4, line4Text.split(''));

        const line5 = document.getElementById('line5');
        const line5Text = 'Profit Quota: 0 / 2054';
        await typewriter(line5, line5Text.split(''));

    });
</script>
<div class="container mx-auto" style="padding-top: 3rem">
    <div id="title" style="font-size: 2rem"></div>
    <div id="line1" style="font-size: 1rem"></div>
    <div id="line2" style="font-size: 0.5rem"></div>
    <div id="line3" style="font-size: 2rem"></div>
    <div id="line4" style="font-size: 3rem"></div>
    <div id="line5" style="font-size: 4rem"></div>
</div>
<style>
    @font-face {
        font-family: 'ibm_3270regular';
        src: url('$lib/fonts/3270/3270-regular-webfont.woff2') format('woff2'),
        url('$lib/fonts/3270/3270-regular-webfont.woff') format('woff');
        font-weight: normal;
        font-style: normal;

    }

    :global(html) {
        background-color: black;
        color: limegreen;
        font-family: 'ibm_3270regular', monospace;
    }

    .container {
        width: 100%;
    }

    /* For screens wider than 640px */
    @media (min-width: 640px) {
        .container {
            max-width: 640px;
        }
    }

    /* For screens wider than 768px */
    @media (min-width: 768px) {
        .container {
            max-width: 768px;
        }
    }

    /* For screens wider than 1024px */
    @media (min-width: 1024px) {
        .container {
            max-width: 1024px;
        }
    }

    /* For screens wider than 1280px */
    @media (min-width: 1280px) {
        .container {
            max-width: 1280px;
        }
    }

    /* For screens wider than 1536px */
    @media (min-width: 1536px) {
        .container {
            max-width: 1536px;
        }
    }

    .mx-auto {
        margin-left: auto;
        margin-right: auto;
    }

    div {
        margin-bottom: 0.75rem;
    }
</style>
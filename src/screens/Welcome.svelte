<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    let selected = false;

    const select = (category) => {
        selected = true;
        dispatch('select', { category });
    }

    const categories = [
        { slug: 'actors', label: 'Actors' },
        { slug: 'athletes', label: 'Athletes' },
        { slug: 'comedians', label: 'Comedians' },
        { slug: 'creators', label: 'Creators' },
        { slug: 'models', label: 'Models' },
        { slug: 'musicians', label: 'Musicians' },
        { slug: 'reality-ty', label: 'Reality TV' }
    ]
</script>

<header>
    <h1>
        CameoP<span class="logo">a</span>rison
    </h1>

    <p class="svelte-1fhxxll">
        On <a href="https://cameo.com">cameo.com</a>, you can buy personalised video clips from everyone from Lindsay Lohan to Ice T.
    </p>

    <p>But who commands the highest price?</p>
</header>

<p>Pick a category to play a game</p>

<div class="categories">
    {#each categories as category}
        <button disabled={selected} on:click={() => select(category)}>{category.label}</button>
    {/each}
</div>

<style>
    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: min(12vw, 4em);
        font-weight: 100;
        margin: 0 0 0.5em 0;
    }
    p {
        max-width: 24em;
        margin: 0 auto 1em auto;
    }
    .logo {
        display: inline-block;
        background: url(/icons/compare.svg) 50% 50% no-repeat;
        background-size: auto;
        background-size: 100% 100%;
        width: 0.8em;
        top: 0.05em;
        transform: scale(1.4);
        left: 0.02em;
        text-indent: -9999px;
    }
</style>

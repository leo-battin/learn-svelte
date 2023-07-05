<script>
    export let colors;
    let selected = colors[0];
</script>

<h1 style='color: {selected}'>Pick a color</h1>

<div>
    {#each colors as color, i (color)}
        <button
            class="color"
            aria-current={selected === color}
            aria-label={color}
            style="background: {color}"
            on:click={() => selected = color}
        >{i + 1}</button>
    {/each}
</div>

<style>
    h1 {
        transition: color 0.7s;
    }

    div {
        display: grid;
        grid-template-columns: repeat(7, 1fr);
        grid-gap: 5px;
        max-width: 400px;
    }

    button.color {
        aspect-ratio: 1;
        border-radius: 50%;
        filter: drop-shadow(2px 2px 3px rgba(0, 0, 0, 0.2));
        transition: all 0.1s;
        border: none;
    }

    button[aria-current="true"] {
        transform: -2px -2px;
        filter: none;
        box-shadow: inset 3px 3px 4px rgba(0, 0, 0, 0.2)
    }
</style>
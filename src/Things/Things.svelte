<script>
  import Youtube from "../Youtube.svelte";
  import Thing from "./Thing.svelte";

  let things = [
    { id: 1, name: "apple" },
    { id: 2, name: "banana" },
    { id: 3, name: "carrot" },
  ];

  let handleClick = () => {
    things = things.slice(1);
  };
</script>

<button on:click={handleClick}> Remove first thing </button>

<p>Keyed : elements are shifted</p>
{#each things as thing (thing.id)}
  <Thing name={thing.name} />
{/each}
<hr />
<p>Unkeyed : elements are replaced</p>
{#each things as thing}
  <Thing name={thing.name} />
{/each}
<p>Understand more :</p>
<Youtube
  iframe={`
    <iframe
      src="https://www.youtube.com/embed/kN4R29zbh7g"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen
    />
  `}
/>

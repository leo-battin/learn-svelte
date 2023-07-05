<script>
  import Child from "../Child.svelte";
  import Nav from "../Nav.svelte";
  import ColorPicker from "../ColorPicker.svelte";
  import Things from "../Things/Things.svelte";
  import Promise from "../Promise.svelte";

  const name = "Léo";
  const src =
    "https://media.tenor.com/ZJgPmB2A0gkAAAAC/knowledge-is-power-gwangi.gif";
  const html =
    "HTML strings can also be rendered using this technique. <strong>Caution: no sanitization is perfomed!</strong>";

  let count = 0;
  $: doubled = count * 2;
  $: console.log(
    `Reactive statements are also a thing! I depend on doubled, which is currently ${doubled}.`
  );
  const increment = () => count++;

  let values = [1, 2, 3];
  const createString = (arr) => {
    let string = "";
    arr.forEach((num) => {
      string += num + ", ";
    });
    return string.slice(0, -2);
  };

  const props = {
    name: "Gigachad",
    arr: ["Hola", "que", "tal?"],
  };

  const colors = ["red", "yellow", "green", "cyan", "blue", "magenta"];
</script>

<Nav />
<h1>Welcome, {name}!</h1>
<p>Your name in all caps would be: {name.toUpperCase()}.</p>
<hr />
<p>Regular HTML attributes can also be dynamically set.</p>
<img {src} alt="A knowledge is power animation" />
<hr />
<p>{@html html}</p>
<hr />
<button on:click={increment}>Click me</button>
<p>
  Let's be reactive! Clicked <strong>{count}</strong>
  {count === 1 ? "time" : "times"}.
</p>
<hr />
<p>
  Doubling the count is easy! Twice the amount of clicks is <strong
    >{doubled}</strong
  >.
</p>
<hr />
<p>Svelte reactivity is triggered by assignements.</p>
<p>Array content is currently {createString(values)}.</p>
<button on:click={() => values.push(values[values.length - 1] + 1)}
  >Push a number</button
>
<button on:click={() => (values = [...values, values[values.length - 1] + 1])}
  >Reassign array</button
>
<hr />
<p>
  In order to pass data from parent to child, just export the property from the
  child.
</p>
<Child name="Léo" arr="['a', 'b', 'c']" />
<Child arr={["a", "b", "c"]} />
<p>Careful with the way objects are passed...</p>
<hr />
<p>
  We can also spread props from an object if its keys match the expected
  property name and values match expected value types:
</p>
<Child {...props} />
<hr />
<p>Let's add some logic!</p>
{#if count > 10}
  <p>{count} is greater than 10!</p>
{:else}
  <p>{count} is lower or equal to 10!</p>
{/if}
<hr />
<p>Logic: each blocks</p>
<ColorPicker {colors} />
<hr />
<p>Just things...</p>
<Things />
<hr>
<Promise />


<style>
  p {
    color: goldenrod;
    font-family: cursive;
  }
</style>

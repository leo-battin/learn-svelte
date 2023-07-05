<script>
  import Nav from "../../Nav.svelte";
  import Youtube from "../../Youtube.svelte";
</script>

<Nav />
<p>ARIA stands for Accessible Rich Internet Applications.</p>
<p>
  Its aim is to make web applications more accessible to people with
  disabilities.
</p>
<p>
  If semantic HTML properties and elements exist for a given purpose, it should
  be preferred over using ARIA props on a non-relevant element.
</p>

<Youtube
  iframe={`<iframe
      src="https://www.youtube.com/embed/qdB8SRhqvFc"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen
    />`}
/>

<blockquote cite="https://www.youtube.com/watch?v=qdB8SRhqvFc">
  It is a temptation with accessibility to think it has to be perfect. This is
  technology, these is people. We don't do perfect. [...] Perfect is very much
  the enemy of good.
</blockquote>

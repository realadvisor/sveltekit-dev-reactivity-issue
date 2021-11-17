Create following page in routes

```svelte
<!-- src/routes/[slug].svelte -->
<script>
  import { page } from '$app/stores';
  let p_slug = $page.params.slug;
</script>

<h1>{p_slug}</h1>
<a href={`${p_slug}_x`}>Click me - {p_slug}</a>
```

In production build or in dev build without code edits
p_slug is constant since I visit any page like http://localhost:3000/test

Even if I click on link "Click me - test", p_slug will not change.

This is good expected behaviour.

**Now the issue.**

In dev mode visit http://localhost:3000/test then click on "Click me - test" link _(url will be changed to /test_x)_

Edit `src/routes/[slug].svelte` like add something to h1.

Visit page again at http://localhost:3000/test

Click on link and see that p_slug is equal to `test_x` what is different behaviour from above.

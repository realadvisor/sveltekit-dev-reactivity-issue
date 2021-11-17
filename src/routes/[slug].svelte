<script>
  import { page } from '$app/stores';

  // On prod or without editing in dev p_slug is constant
  // If I visit http://localhost:3000/test, then any click on link will not change p_slug value

  // But if I do any editing in dev and visit http://localhost:3000/test
  // then click on link, I will see that p_slug is equal to test_x
  let p_slug = $page.params.slug;
</script>

<h1>{p_slug}</h1>
<a href={`${p_slug}_x`}>Click me - {p_slug}</a>

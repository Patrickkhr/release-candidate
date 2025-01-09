<script>
  import { Hero2, BookingsForm } from '$lib/index';
  export let items
</script>

<svelte:head>
  <title>Groepsboekingen</title>
</svelte:head>

  <Hero2 {items} />
  <BookingsForm {items} />

<style>
</style>

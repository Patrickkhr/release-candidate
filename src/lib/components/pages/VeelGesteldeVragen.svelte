<script>
    export let items
</script>

<svelte:head>
  <title>Veel Gestelde Vragen </title>
</svelte:head>

<section id="FAQ">
    {#each items[0].componentsCollection.items as item}
      <details>
        <summary>{item.title}</summary>
        <p>{item.textParagraph}</p>
      </details>
    {/each}
</section>
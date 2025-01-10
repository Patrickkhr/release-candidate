<script>
    export let items
</script>

<svelte:head>
  <title>Veel Gestelde Vragen </title>
</svelte:head>

<section id="FAQ">
    {#each items[0].componentsCollection.items as item}
      <article>
        <p>{item.textTitle}</p>
        <p>{item.textParagraph}</p>
      </article>
    {/each}
</section>
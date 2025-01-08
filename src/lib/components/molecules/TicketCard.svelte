<script>
  import {
    Image,
    RouteIcon,
    CocktailIcon,
    ArrowRightShort,
    IconLocationThin,
    BookIcon,
    Button,
  } from "$lib/index";
  export let itemCollection;
  const items = itemCollection.componentsCollection.items;
</script>

{#each items as item}
  <article>
    <div class="card-header">
      <p>
        <span class="location-icon">
          <IconLocationThin
            width="13"
            height="13"
            fill="var(--txt-dark-clr)"
          /></span
        >
        {item.location}
      </p>
      <p class="cocktail-price">{item.price}</p>
    </div>
    <div class="img-overlay">
      <img
        src={item.image.url}
        alt={item.image.title}
        brdRadius="var(--radius-lg)"
        opacity="0.6"
        loading="lazy"
        width="450"
        height="321"
        title={item.image.title.replace(/\s+/g, "-")}
      />
      <h2>{item.title}</h2>
    </div>
    <div class="card-description">
      <ul>
        <li>
          <span
            ><RouteIcon
              width="20"
              height="20"
              fill="var(--page-bg-color)"
            /></span
          >
          {item.location}
        </li>
        <li>
          <span
            ><CocktailIcon
              width="20"
              height="20"
              fill="var(--page-bg-color)"
            /></span
          >
          {item.cocktailDescription}
        </li>
      </ul>
    </div>

    <!-- Book Icon toevoegen -->

    <div class="card-buttons">
      <Button
        type="button"
        variant="tertiary"
        title="Boek nu"
        icon={BookIcon}
        iconColor="var(--txt-quaternary-clr)"
        size="s"
      />
      <Button
        href="/home/{item.slug}"
        variant="secondary"
        title="Lees Meer"
        icon={ArrowRightShort}
        size="s"
      />
    </div>
  </article>
{/each}

<style>
  .card-header {
    display: flex;
    justify-content: space-between;
    padding: 0.5em;
  }

  .cocktail-price {
    border: 1px solid #3f2b21;
    border-radius: 8px;
    padding: 0.2em;
  }

  article {
    display: block;
    width: 100%;
    max-width: 350px;
    border: 1px solid #ccc;
    border-radius: 8px;
    background-color: #ffe5d9;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    overflow: hidden;
  }

  @media screen and (min-width: 768px) {
    article {
      width: 80%;
      max-width: 350px;
    }
  }

  article img {
    position: relative;
    background-color: black;
    display: block;
    object-fit: cover;
    width: 350px;
    height: 250px;
    filter: brightness(0.5);
  }

  h2 {
    padding-left: 0.5em;
    padding-top: 0.5em;
    font-size: 20px;
    letter-spacing: 2px;
  }

  .card-description {
    padding-left: 0.5em;
  }

  li {
    padding-top: 0.4em;
  }

  .card-buttons {
    width: 100%;
    display: flex;
    flex-direction: column;
    transform: scale(0.9);
    margin: 1em 1.5em 1em 0;
    gap: 1em;
  }

  @media screen and (min-width: 768px) {
    .card-buttons {
      flex-direction: unset;
      transform: none;
      margin: 1em 1.6em 1em 1.6em;
      padding-right: 15px;
      gap: 2em;
    }
  }

  p:first-child {
    padding-top: 0.3em;
  }

  span {
    padding-left: 0.5em;
  }
</style>

<script>
  import { Filter, TicketCard } from "$lib/index";
  export let itemCollection;
</script>

<section class="intro">
  <h1>Tours</h1>
  <ul>
    <li>Amsterdam</li>
    <li>Rotterdam</li>
    <li>Utrecht</li>
  </ul>
</section>

<section class="tours">
  <TicketCard {itemCollection} />
</section>

<style>
  .intro {
    background-color: #3f2b21;
    margin-top: 8em;
    padding: 2em;
    width: 100%;
  }

  ul {
    display: flex;
    list-style: none;
    justify-content: center;

    padding-top: 0.5em;
    padding-right: 2em;
    font-size: 14px;

    @media (min-width: 768px) {
      font-size: 16px;
    }
  }

  li {
    color: #ffe5d9;
    cursor: pointer;
    padding: 0.5em 1em 0 2em;
  }

  li:hover {
    color: #ffaa81;
  }

  .intro ul li::after {
    content: "";
    width: 0%;
    height: 2px;
    background: #ffaa81;
    display: block;
    margin: auto;
    transition: 0.5s;
  }

  .intro ul li:hover::after {
    width: 100%;
  }

  h1 {
    text-align: center;
    color: #ffaa81;
    font-size: 3.5rem;
  }

  .tours {
    width: 60%;
    max-width: 100vw;
    min-width: 300px;
    margin: 0 auto;
    margin-top: 2em;
    margin-bottom: 2em;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: 20px;
  }
</style>
